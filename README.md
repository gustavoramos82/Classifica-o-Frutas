# Classifição Frutas
Estudando Machine learning usando esse dataset de classificação de frutas, cujo link pode ser acessado [aqui](https://www.kaggle.com/datasets/muratkokludataset/date-fruit-datasets),usando como classificação o metodo do random forest, knn e naive bayes

  Como a classificação das frutas esta distribuidada dessa forma:

![image](https://user-images.githubusercontent.com/39843884/167215373-3da7f7f1-c333-433a-8853-f12b842a43e6.png)

  Decidi separa em dois dataframs uma com as três primeiras frutas e outra com as outras frutas, como o primeiro dataframe obteve o seguinte resultados

![image](https://user-images.githubusercontent.com/39843884/167215680-6491fe04-6cfc-4868-93e9-5bf161016cfe.png)

  A primeira vista naive bayes perfoma melhor, mas como tem em todos uma suspeitas de overfitting, o intuito é usar cross-validation para verificar esses resultado e depois ver o outro dataframe.
