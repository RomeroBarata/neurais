Amostragem dos dados
=====================
Esse documento explicita como irá funcionar o processo de amostragem do projeto.

O processo de amostragem tem como objetivo particionar os dados em três subgrupos (treinamento, validação e teste).
Para obter esses grupos de dados utilizaremos tanto métodos simples como a replicação aleatória e a redução 
aleatória, como métodos mais complexos como a replicação com SMOTE e SMOTE modificado.

O processo se dará em quatro etapas:

##### Etapa 1:
Nessa etapa o objetivo é dividir os dados de acordo com as duas classes do problema. Ou seja, como resultado dessa 
etapas iremos obter um primeiro subgrupo dos dados que irá conter apenas os dados relativos aos pacientes que 
tiveram resultado positivos nos exames, já o segundo grupo irá conter os dados relativos aos pacientes que tiveram
resultado negativos nos exames.

##### Etapa 2:
Dividir cada subgrupo em treiamento, validacao e teste

##### Etapa 3:
replicar/reduzir os conjuntos de treinamento e validacao

##### Etapa 4:
juntar os grupos de treinamento, validacao e teste de cada classe em um unico grupo.
