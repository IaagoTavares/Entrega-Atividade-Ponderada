# Atividade: Animal Pose Estimation
## 1. Análise Exploratória

### 1.1 Aplicação de Keypoints

Inicialmente é feita uma seleção aleatoria de 20 imagens do conjunto de dados e as exibe em um grid. Cada imagem é mostrada com suas caixas delimitadoras e pontos-chave desenhados sobre ela. As imagens são organizadas em um layout de várias linhas e colunas para facilitar a visualização.

<img src="./img/data_aug3.png" alt="Gráfico de Número de imagens por dimensão" width="1000"/>


### 1.2 Quantidade de imagens por categoria 

<img src="./img/data_aug2.png" alt="Gráfico de Número de imagens por dimensão" width="1000"/>

A predominância de imagens no formato paisagem (80%) indica que a maioria das capturas dos animais é feita de forma horizontal. As imagens em formato retrato (19%) e quadradas (1%) são significativamente menos frequentes, o que indica que ajustes específicos podem ser necessários para lidar com esses formatos ao desenvolver modelos de detecção.


## 2. Filtragem e Processamento

Na filtragem, é aplicada uma função para pré-processar e aumentar imagens. A função redimensiona as imagens, aplica transformações aleatórias (como flip, escala, translação e rotação) e normaliza tanto os valores dos pixels quanto as coordenadas dos pontos-chave. Isso ajuda a aumentar a variedade dos dados de treinamento e a preparar as imagens de forma consistente para o modelo.

<img src="./img/data_aug.png" alt="Gráfico de Número de imagens por dimensão" width="1000"/>

## 4. Conclusões

### Principais Aprendizados

Essa análise exploratória me ajudou a exercitar e entender melhor a distribuição e as características das imagens no meu conjunto de dados, como os formatos predominantes e a presença de pontos-chave. Acredito que alguns pontos de aprendizado poderão ser utilizados no meu projeto com a finalidade de melhorar a performance do modelo.