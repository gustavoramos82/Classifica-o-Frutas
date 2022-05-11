# Classificação das Frutas

Estudando Machine learning usando esse dataset de classificação de frutas, cujo link pode ser acessado [aqui](https://www.kaggle.com/datasets/muratkokludataset/date-fruit-datasets),usando como classificação o metodo do random forest, knn e naive bayes

  Como a classificação das frutas esta distribuidada dessa forma:

![image](https://user-images.githubusercontent.com/39843884/167215373-3da7f7f1-c333-433a-8853-f12b842a43e6.png)

  Decidi separa em dois dataframes uma com as três primeiras frutas (do qual chamei de frutas1) e outra com as outras frutas (do qual chamei de frutas 2), como o primeiro dataframe obteve o seguinte resultados

![image](https://user-images.githubusercontent.com/39843884/167215680-6491fe04-6cfc-4868-93e9-5bf161016cfe.png)

  A primeira vista naive bayes perfoma melhor, mas como tem em todos uma suspeitas de overfitting, o intuito é usar *cross-validation* para verificar esses resultado.
  
  Quando a outro dataframe, temos o seguinte resultado observando tanto a matriz de confusão, quanto as métricas.
  
  ![image](https://user-images.githubusercontent.com/39843884/167431515-054f4b5e-fad1-4d72-a41f-8e055eae0ace.png)

![image](https://user-images.githubusercontent.com/39843884/167431851-3e8c1cc2-beca-4759-a268-ae462ee1abba.png)
![image](https://user-images.githubusercontent.com/39843884/167431915-2b97cdf9-6b2a-4808-a2b6-038e2640b1a4.png)

Podemos ver que o **random forest** e o **naive bayes** foram os que tiveram a melhor perfomace para esses conjuntos de dados, mas como o processamento do random forest é muito maior, escolheria o naive bayes para prever os resultados, já que os resultados são praticamente os mesmos.

Agora, o intuito é usar o cross validation para o primeiro dataframe e usar verificar se usando menos variaveis, o modelo tem quase que a mesma perfomace que usando todas as variaveis. 

Fazendo o cross validation temos o seguinte resultados com o primeiro dataframe, temos o seguinte resultados com 7 folds.
Com **Random Forest**:

![image](https://user-images.githubusercontent.com/39843884/167817700-325432af-f8b2-4c5a-b32e-2f3260333af3.png)

Com **Naive Bayes**:

![image](https://user-images.githubusercontent.com/39843884/167818033-35201ea9-a35a-4ac1-bc3d-a5a508f56f1f.png)

Com **Knn**:

![image](https://user-images.githubusercontent.com/39843884/167818206-28776d09-cedc-450c-8b40-33487f1e70d7.png)
 
 Podemos ver que com os três modelos os três perfomaram bem, então pelo processamento, poderia escolher ou o naive bayes ou o knn.
 
 ## Selecionando 12 colunas para verificar se o modelo tem uma boa perfomace
 
 Agora selecionamos algumas colunas (foram escolhidas 12) mas foram feitas algumas coisas antes, como: tirar umas colunas que não tinha uma grande variação e tirar colunas que tinha uma grande correlação com outras. Um exmplo pra se ver é a coluna *SOLIDITY*,conforme pode-se ver no gráfico abaixo:
 
 ![image](https://user-images.githubusercontent.com/39843884/167819377-9b6a514b-b192-4a10-b0b8-98aac7c6cb61.png)

Assim, e usando o RFE, usamos essas 12 colunas: *'AREA', 'SHAPEFACTOR_4', 'MeanRR', 'MeanRG', 'MeanRB', 'SkewRG',
       'KurtosisRG', 'EntropyRR', 'EntropyRG', 'EntropyRB', 'ALLdaub4RR',
       'ALLdaub4RG*.

Quanto as frutas um teve um bom desempenho nos três, conforme pode ser visto abaixo dividindo em 8 folds:

**Random Forest**:

![image](https://user-images.githubusercontent.com/39843884/167820259-3433f538-bc2f-4637-904e-9e703653d817.png)

**Naive Bayes**:

![image](https://user-images.githubusercontent.com/39843884/167821509-58e158b9-ffea-4680-a03b-16a6133d9720.png)

**Knn**:

![image](https://user-images.githubusercontent.com/39843884/167824103-06799801-e96c-4a56-8ba2-b7c5d6e2919d.png)

Podemos ver que não temos quase nada de perda de perfomace quanto considerando todas as 35 colunas, e todos os 3 modelos teve uma boa perfomace, com muita pouca diferença nos resultados.

![output](https://user-images.githubusercontent.com/39843884/167827250-4cf9efb5-c553-4685-b191-0316f97fc828.png)

Olhando as metricas, temos os seguintes resultados:

![image](https://user-images.githubusercontent.com/39843884/167827977-4177b9a2-c0cd-4fa5-adc1-32820a96c1a5.png)
![image](https://user-images.githubusercontent.com/39843884/167828025-293c47b3-a846-4eca-bc5a-994da517596a.png)

Nesse caso, tivemos um pouco de perda de perfomace, mas os modelos até que classificaram bem, em especial o random forest e o knn, então depedendo do caso, poderia usar somente essas 12 colunas.

