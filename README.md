# LDA - Análise Discriminante Linear

É um método de aprendizado de máquina supervisionado que resolve problemas de classificação multiclasse. A LDA separa múltiplas classes com múltiplas funcionalidades por meio da redução da dimensionalidade dos dados. Os algoritmos modela a distribuição dos dados para cada classe e utilizam o ``Teorema de Bayes`` para classificar novos pontos de dados. O ``Teorema de Bayes`` calcula a probabilidade condicional (probabilidade de um evento ocorrer dado que um evenjo já ocorreu). A LDA é usado para aprimorar o funcionamento de outros algoritos de classificação, como ``Árvore de Decisão``, ``Floresta Aleatória`` e ``SVM``.

---

## Propriedades da LDA

A LDA projeta dados de um espaço com n dimensões para um espaço reduzido de k = n - 1, preservando a separação entre as classes. Ele utiliza propriedades estatísticas como médias e matriz de covariância, assumindo que os dados seguem uma distribuição Gaussiana multivariada.

**O modelo parte das seguintes suposições:**

- Os dados seguem uma distribuição normal (curva em sino);

- As classes são linearmente separáveis;

- Todas as classes compartilham a mesma matriz de covariância.

Devido a essas restrições, o desempenho do LDA pode ser limitado em espaços de alta dimensionalidade.

---

## Autovalores e Autovetores

Na redução de dimensionalidade, o LDA utiliza autovalores e autovetores para analisar transformações lineares.

- Autovetores indicam as direções mais relevantes no espaço dos dados.

- Autovalores medem a importância dessas direções — quanto maior o autovalor, mais relevante a direção.

Esses elementos são obtidos a partir de duas matrizes:

- Matriz de dispersão entre classes: mostra como as classes estão separadas entre si.

- Matriz de dispersão dentro das classes: mostra a variação dos dados dentro de cada classe.

---

## Etapas para implementar a LDA

1) Pŕe-processar os dados: normalizar e centralizar os dados;

2) Escolher o número de componentes: definir ``n_components`` para indicar quantos discriminantes lineares serão usados;

3) Regularizar o modelo: ajuda a evitar overfitting;

4) Aplicar validação cruzada: avaliar a performance do modelo de forma mais confiǘel.

---

## Funcionamento da função discriminante da LDA

- Calcula a variância entre classes: mede o quão separadas estão as classes;

- Calcula a variância dentro das classes: mede a dispersão dos dados em cada classe;

- Projeta os dados em um novo espaço: maximiza a separação entre classes e minimiza a variação dentro das classes, otimizando a classificação.

---

## Parâmetros no Scikit-Learn

- **n_components:** número de componentes lineares (máx = número de classes - 1);

- **solver:** algoritmo de solução (sdv : Ṕadrão, lsqr: Quando quer usar regularização, eigen: Quando quer armazenar matriz de covariância e usar ``shrinkage``);

- **shrinkage:** regularização (só funciona com lsqr ou eigen), usar quando os dados forem de alta dimensionalidade;

- **priors:** probabilidades a priori das classes, usar quando as classes são desbalanceadas;

- **store_covariance:** se ``True``, armazena a matriz de covariância;

- **tol:** tolerãncia numérica para parada.

## Vantagens

- Utilizar simplicidade e eficiência de computação;

- Lidar com multicolinearidade e multiclasses;

---

## Desvantagens

- Não é adequado para dados não rotulados;

- Distribuições de médias compartilhadas: O LDA enfrenta desafios quando as distribuições das classes possuem médias iguais. O LDA tem dificuldade em criar um novo eixo que separe linearmente ambas as classes.