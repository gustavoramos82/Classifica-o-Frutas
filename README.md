# Classificação das Frutas

Estudando Machine learning usando esse dataset de classificação de frutas, cujo link pode ser acessado [aqui](https://www.kaggle.com/datasets/muratkokludataset/date-fruit-datasets),usando como classificação o metodo do random forest, knn e naive bayes

  Como a classificação das frutas esta distribuidada dessa forma:

![image](https://user-images.githubusercontent.com/39843884/167215373-3da7f7f1-c333-433a-8853-f12b842a43e6.png)

  Decidi separa em dois dataframs uma com as três primeiras frutas e outra com as outras frutas, como o primeiro dataframe obteve o seguinte resultados

![image](https://user-images.githubusercontent.com/39843884/167215680-6491fe04-6cfc-4868-93e9-5bf161016cfe.png)

  A primeira vista naive bayes perfoma melhor, mas como tem em todos uma suspeitas de overfitting, o intuito é usar *cross-validation* para verificar esses resultado.
  
  Quando a outro dataframe, temos o seguinte resultado observando tanto a matriz de confusão, quanto as métricas.
  
  ![image](https://user-images.githubusercontent.com/39843884/167431515-054f4b5e-fad1-4d72-a41f-8e055eae0ace.png)

![image](https://user-images.githubusercontent.com/39843884/167431851-3e8c1cc2-beca-4759-a268-ae462ee1abba.png)
![image](https://user-images.githubusercontent.com/39843884/167431915-2b97cdf9-6b2a-4808-a2b6-038e2640b1a4.png)

Podemos ver que o **random forest** e o **naive bayes** foram os que tiveram a melhor perfomace para esses conjuntos de dados, mas como o processamento do random forest é muito maior, escolheria o naive bayes para prever os resultados, já que os resultados são praticamente os mesmos.

Agora, o intuito é usar o cross validation para o primeiro dataframe e usar verificar se usando menos variaveis, o modelo tem quase que a mesma perfomace que usando todas as variaveis. 
