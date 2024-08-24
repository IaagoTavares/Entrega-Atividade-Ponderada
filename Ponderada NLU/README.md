# Relatório de Classificação de Intenções utilizando TensorFlow Embedding e Word2Vec

## 1. Introdução

Este projeto visa construir e avaliar um classificador de intenções para um chatbot, utilizando duas abordagens distintas de vetorização de texto: Embedding Layer do TensorFlow e Word2Vec. As métricas de desempenho, incluindo acurácia, recall e f1-score, são comparadas para as duas abordagens.

## 2. Preparação dos Dados

Os dados utilizados consistem em perguntas categorizadas em diferentes intenções. As etapas de preparação incluem:

- **Tokenização**: Separação das perguntas em tokens (palavras).
- **Codificação das Intenções**: Conversão das intenções para valores numéricos usando LabelEncoder.
- **Divisão de Dados**: Separação dos dados em conjuntos de treino (80%) e teste (20%).

## 3. Vetorização usando TensorFlow Embedding

### 3.1. Definição do Modelo

Um modelo de rede neural sequencial foi criado com as seguintes camadas:

- **Embedding Layer**: Vetorização das palavras.
- **GlobalAveragePooling1D**: Agregação dos vetores.
- **Dense Layers**: Camadas densas com função de ativação ReLU.
- **Output Layer**: Camada de saída com função de ativação softmax para classificação.

```python
modelo = tf.keras.Sequential([
    tf.keras.layers.Embedding(input_dim=5000, output_dim=16, input_length=comprimento_maximo),
    tf.keras.layers.GlobalAveragePooling1D(),
    tf.keras.layers.Dense(24, activation='relu'),
    tf.keras.layers.Dense(12, activation='relu'),
    tf.keras.layers.Dense(len(codificador_labels.classes_), activation='softmax')
])

modelo.compile(loss='sparse_categorical_crossentropy',
               optimizer='adam',
               metrics=['accuracy'])

modelo.summary()

```

## 4. Vetorização usando Word2Vec

### 4.1. Treinamento com o Word2Vec

As frases foram tokenizadas e utilizadas para treinar um modelo Word2Vec.

```python

tokens_treino = [frase.split() for frase em perguntas_treino]
tokens_teste = [frase.split() for frase em perguntas_teste]

modelo_word2vec = Word2Vec(sentences=tokens_treino, vector_size=100, window=5, min_count=1, workers=4)
```

### 4.2. Conversão das frases em vetores 

As frases foram convertidas em vetores de caracteristicas utilizando a média dos vetores das palavras. 

```python
vetores_treino_w2v = np.array([frase_para_vetor(frase, modelo_word2vec, 100) for frase em perguntas_treino])
vetores_teste_w2v = np.array([frase_para_vetor(frase, modelo_word2vec, 100) for frase em perguntas_teste])
```

### 4.3. Treinamento do classificador
Foi utilizado um classificador RandomForest para treinar o modelo a partir dos vetores Word2Vec.

```python
classificador = RandomForestClassifier(n_estimators=100, random_state=42)

classificador.fit(vetores_treino_w2v, intencoes_treino)

previsoes_w2v = classificador.predict(vetores_teste_w2v)

```

## Comparação dos resultados

```python
TensorFlow Embedding 
- Acurácia: 0.15841584158415842
- Recall: 0.15841584158415842
- F1-Score: 0.04332740966404333

Word2Vec
- Acurácia: 0.39603960396039606
- Recall: 0.39603960396039606
- F1-Score: 0.2917149942842385
```

Os resultados das duas abordagens foram comparados com base nas seguintes métricas:

- *Acurácia*: Word2Vec apresentou um resultado melhor.
- *Recall*: Word2Vec apresentou um resultado melhor.
- *F1-Score*: Word2Vec apresentou um resultado melhor.

