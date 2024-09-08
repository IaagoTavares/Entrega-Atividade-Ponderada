*1- Tente valores diferentes do argumento num_examples na funçãoload_data_nmt. Como isso afeta os tamanhos do vocabulário do idioma de origem e do idioma de destino?*

### Aumento do num_steps
Com mais exemplos, o modelo teve acesso a um conjunto maior de dados de tradução.Com isso uma variedade maior de palavras foi observada no conjunto de treinamento, tanto no idioma de origem quanto no idioma de destino.Consequentemente, os vocabulários de ambos os idiomas (tanto o de origem quanto o de destino) foram maiores, já que mais palavras foram adicionadas às listas de vocabulário.


### Redução do num_steps
Ao reduzir o número de exemplos, um numero menor de dados de tradução foram usados. Isso resultou em menos diversidade de palavras no conjunto de treinamento. Os vocabulários também ficaram menores porque menos palavras estavam presentes nos dados.


*2- O texto em alguns idiomas, como chinês e japonês, não tem indicadores de limite de palavras (por exemplo, espaço). A tokenização em nível de palavra ainda é uma boa ideia para esses casos? Por que ou por que não?*

A tokenização em nível de palavra não é adequada para idiomas como chinês e japonês, que não possuem espaços para delimitar palavras. Utilizar a função split(' ') nesses idiomas resultaria em tokenização por caractere, o que não captura corretamente as unidades de significado. Em vez disso, é melhor usar ferramentas específicas como jieba para chinês e Mecab para japonês ou aplicar técnicas de tokenização em subpalavras como Byte Pair Encoding (BPE), que são mais eficazes para segmentar corretamente o texto nesses idiomas.