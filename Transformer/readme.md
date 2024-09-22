# Atividade de tradução com transformer

O codigo presente no arquivo Atividade_Transformer_Iago_Tavares.ipynb implementa um modelo Transformer para tradução de texto. O notebook inclui o carregamento de um modelo pré-treinado e o processo de inferência para traduzir sentenças do português para o inglês. Durante a execução, não foi possivel executar completamente o treinamento do modelo por conta do alto tempo de execução.  

![alt text](./Imagem%20treinamento.PNG)


## Pontos positivos

**Uso do Transformer**: O projeto utiliza a arquitetura Transformer, que é uma das mais avançadas e eficazes para tarefas de tradução e NLP em geral.


**Modelo pré-treinado**: A utilização de um modelo pré-treinado acelera o processo e melhora a performance, evitando a necessidade 
de treinar do zero.


**Salvamento e recarregamento do modelo**: A funcionalidade de salvar e recarregar o modelo facilita a reutilização e a aplicação prática em diferentes ambientes.



## Ponto negativo

**Elevado custo computacional**: O tempo demandado para o treinamento do modelo foi consideravelmente longo, mesmo com o uso de uma GPU. Isso pode ser um obstáculo para quem não dispõe de recursos computacionais de alto desempenho, restringindo a acessibilidade do modelo para aprendizado e testes rápidos. 