Processo de Experimentação
=====================
Esse documento explicita como irá funcionar o processo de experimentação do projeto.

O processo de experimentação se dará a partir da avaliação do desempenho da rede neural utilizando várias combinações de possíveis valores dos seus parâmetros.

Os parâmetros e seus valores são os seguintes:
  * Fixos:
    * Critério de gradiente minimo [0]
    * Critério mínimo de erro de treinamento  [0]
    * Critério de quantidade máxima de falhas na validação [10]
    * Número máximo de iterações [10000]
  * Variáveis:
    * Taxa de apredizagem [0.01, 0.1, 0.5, 0.9]
    * Número de nós na camada intermediária [3, 6, 12]
    * Algoritmo de aprendizagem [Levenberg-Marquardt: 'trainlm' ; Gradient descent with momentum backpropagation: 'traingdm' ; Resilient backpropagation: 'trainrp']
    * Função de ativação [Hyperbolic tangent sigmoid transfer function: 'tansig' ; Log-sigmoid transfer function: 'logsig']
 
##### Etapa 1:
Nessa etapa iremos variar a taxa de aprendizagem e o número de nós da camada intermediária e testar todas as
combinações possíveis. Para isso iremos utilizar a replicação simples como método de sampling. Os testes serão feitos da seguinte forma:
  * Nós = 3 e Taxa = 0.01
  * Nós = 3 e Taxa = 0.1
  * Nós = 3 e Taxa = 0.5
  * Nós = 3 e Taxa = 0.9
  * Nós = 6 e Taxa = 0.01
  * Nós = 6 e Taxa = 0.1
  * Nós = 6 e Taxa = 0.5
  * Nós = 6 e Taxa = 0.9
  * Nós = 12 e Taxa = 0.01
  * Nós = 12 e Taxa = 0.1
  * Nós = 12 e Taxa = 0.5
  * Nós = 12 e Taxa = 0.9

As melhores combinações foram:
  * Comb 1 => Nós = 3 e Taxa = 0.01
  * Comb 2 => Nós = 6 e Taxa = 0.01
  * Comb 3 => Nós = 12 e Taxa = 0.1

##### Etapa 2:
Nessa segunda etapa iremos selecionar as 3 melhores combinações (comb1, comb2 e comb3) da etapa anterior e variar elas juntamente com os algoritmos de aprendizagem selecionados (trainlm, traingdm e trainrp). Os testes serão feitos da seguinte forma:
  * trainlm e Comb1 (Nós = 3 e Taxa = 0.01)
  * trainlm e Comb2 (Nós = 6 e Taxa = 0.01)
  * trainlm e Comb3 (Nós = 12 e Taxa = 0.1)
  * traingdm e Comb1 (Nós = 3 e Taxa = 0.01)
  * traingdm e Comb2 (Nós = 6 e Taxa = 0.01)
  * traingdm e Comb3 (Nós = 12 e Taxa = 0.1)
  * trainrp e Comb1 (Nós = 3 e Taxa = 0.01)
  * trainrp e Comb2 (Nós = 6 e Taxa = 0.01)
  * trainrp e Comb3 (Nós = 12 e Taxa = 0.1)

As melhores combinações foram:
  * Comb 1 => trainlm, Nós = 3 e Taxa = 0.01
  * Comb 2 => trainlm, Nós = 6 e Taxa = 0.01
  * Comb 3 => trainlm, Nós = 12 e Taxa = 0.1

##### Etapa 3:
Nessa terceira etapa iremos selecionar as 3 melhores combinações (comb1, comb2 e comb3) da etapa anterior e variar elas juntamente com funções de ativação selecionadas (tansig, logsig). Os testes serão feitos da seguinte forma:
  * tansig e Comb1 (trainlm, Nós = 3 e Taxa = 0.01)
  * tansig e Comb2 (trainlm, Nós = 6 e Taxa = 0.01)
  * tansig e Comb3 (trainlm, Nós = 12 e Taxa = 0.1)
  * logsig e Comb1 (trainlm, Nós = 3 e Taxa = 0.01)
  * logsig e Comb2 (trainlm, Nós = 6 e Taxa = 0.01)
  * logsig e Comb3 (trainlm, Nós = 12 e Taxa = 0.1)

As melhores combinações foram:
  * Comb 1 => logsig, trainlm, Nós = 3 e Taxa = 0.01
  * Comb 2 => tansig, trainlm, Nós = 6 e Taxa = 0.01

##### Etapa 4:
Nessa quarta etapa iremos selecionar as 2 melhores combinações (comb1 e comb2) da etapa anterior e variar elas juntamente com os métodos de sampling selecionados (replicação, redução, SMOTE e SMOTE modificado). Os testes serão feitos da seguinte forma:
  * Replicação e Comb1 (logsig, trainlm, Nós = 3 e Taxa = 0.01)
  * Replicação e Comb2 (tansig, trainlm, Nós = 6 e Taxa = 0.01)
  * Redução e Comb1 (logsig, trainlm, Nós = 3 e Taxa = 0.01)
  * Redução e Comb2 (tansig, trainlm, Nós = 6 e Taxa = 0.01)
  * SMOTE k = 3 e Comb1 (logsig, trainlm, Nós = 3 e Taxa = 0.01)
  * SMOTE k = 3 e Comb2 (tansig, trainlm, Nós = 6 e Taxa = 0.01)
  * SMOTE k = 5 e Comb1 (logsig, trainlm, Nós = 3 e Taxa = 0.01)
  * SMOTE k = 5 e Comb2 (tansig, trainlm, Nós = 6 e Taxa = 0.01)
  * SMOTE k = 3 modificado e Comb1 (logsig, trainlm, Nós = 3 e Taxa = 0.01)
  * SMOTE k = 3 modificado e Comb2 (tansig, trainlm, Nós = 6 e Taxa = 0.01)
  * SMOTE k = 5 modificado e Comb1 (logsig, trainlm, Nós = 3 e Taxa = 0.01)
  * SMOTE k = 5 modificado e Comb2 (tansig, trainlm, Nós = 6 e Taxa = 0.01)

A partir de todos esses testes e dos métodos de avaliação que utilizaremos (MSE, Curva ROC e Matriz de Confusão) será possível analisar qual a melhor combinação de parâmetros para resolver o problema proposto.
