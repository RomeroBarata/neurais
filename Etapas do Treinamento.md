Etapas do Treinamento
=====================
Esse documento explicita como irá funcionar o processo de experimentação do projeto.

O processo de experimentação se dará a partir da avaliação do desempenho da rede neural utilizando várias combinações
de possíveis valores dos seus parâmetros.

Os parâmetros e seus valores são os seguintes:
  * Fixos:
    * Critério de gradiente minimo [10] -- Não sabemos o que significa
    * Critério mínimo de erro de treinamento  [10] -- Não sabemos o que significa
    * Critério de quantidade máxima de falhas na validação [10]
  * Variáveis:
    * Número máximo de iterações [5000, 10000, 20000]
    * Taxa de apredizagem [0.01, 0.1, 0.5, 0.9]
    * Número de nós na camada intermediária [3, 6, 12]

Como iremos avaliar todas as combinações possíveis, serão feitos 36 testes para decidir qual a melhor
combinação de parâmetros.
