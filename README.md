# 🤖 Predição de Planos de Telefonia — Megaline

## 📌 Sobre o Projeto

Este projeto tem como objetivo desenvolver um modelo de Machine Learning capaz de classificar os clientes da operadora Megaline de acordo com o plano de telefonia utilizado: **Smart ou Ultra**.

A partir de dados sobre o comportamento dos usuários, foram desenvolvidos e avaliados diferentes modelos de classificação para identificar aquele com melhor desempenho preditivo.

O projeto foi desenvolvido como parte da formação em **Análise de Dados e Ciência de Dados da TripleTen**, aplicando conceitos de análise exploratória, preparação de dados, treinamento de modelos e avaliação de desempenho.

## 🎯 Objetivos

- Analisar os dados de comportamento dos usuários.
- Preparar os dados para a construção de modelos de Machine Learning.
- Treinar e comparar diferentes algoritmos de classificação.
- Ajustar hiperparâmetros para melhorar o desempenho dos modelos.
- Avaliar o modelo selecionado em um conjunto de teste independente.
- Comparar os resultados com um modelo de referência (*baseline*).

## 🗂️ Conjunto de Dados

O conjunto de dados utilizado foi o `users_behavior.csv`, composto por **3.214 registros e 5 colunas**.

| Variável | Descrição |
|---|---|
| `calls` | Quantidade de chamadas realizadas pelo usuário |
| `minutes` | Total de minutos de chamadas utilizados |
| `messages` | Quantidade de mensagens enviadas |
| `mb_used` | Volume de dados de internet utilizado, em MB |
| `is_ultra` | Variável-alvo que indica se o cliente utiliza o plano Ultra |

A variável `is_ultra` foi definida como o alvo da previsão, enquanto as demais variáveis foram utilizadas como atributos preditores.

Durante a análise inicial, não foram identificados valores ausentes.

## 🛠️ Tecnologias e Bibliotecas

- **Python** — linguagem utilizada no desenvolvimento.
- **Pandas** — manipulação e análise dos dados.
- **Scikit-learn** — treinamento, validação e avaliação dos modelos.
- **Jupyter Notebook** — ambiente de desenvolvimento e documentação das análises.

## ⚙️ Metodologia

O desenvolvimento foi organizado nas seguintes etapas:

1. **Análise exploratória:** inspeção da estrutura do conjunto de dados e verificação de valores ausentes.
2. **Preparação dos dados:** separação entre variáveis preditoras e variável-alvo.
3. **Divisão dos conjuntos:** separação dos dados em 60% para treinamento, 20% para validação e 20% para teste.
4. **Treinamento dos modelos:** implementação de três algoritmos de classificação.
5. **Ajuste de hiperparâmetros:** comparação de diferentes configurações com base na acurácia do conjunto de validação.
6. **Seleção do modelo:** escolha do algoritmo com melhor desempenho na validação.
7. **Avaliação final:** teste do modelo selecionado em dados não utilizados durante o treinamento.
8. **Comparação com baseline:** avaliação do desempenho em relação a um `DummyClassifier`.

## 🤖 Modelos Avaliados

Foram utilizados três algoritmos de classificação:

- **Árvore de Decisão (`DecisionTreeClassifier`):** avaliação de diferentes valores para o parâmetro `max_depth`.
- **Floresta Aleatória (`RandomForestClassifier`):** avaliação de diferentes quantidades de árvores por meio do parâmetro `n_estimators`.
- **Regressão Logística (`LogisticRegression`):** modelo de classificação utilizado para comparação de desempenho.

A métrica utilizada para comparar os modelos foi a **acurácia (*accuracy*)**, que representa a proporção de previsões corretas em relação ao total de previsões realizadas.

## 📈 Resultados Obtidos

### Desempenho no conjunto de validação

| Modelo | Melhor configuração | Acurácia |
|---|---|---:|
| Árvore de Decisão | `max_depth = 3` | **78,54%** |
| Floresta Aleatória | `n_estimators = 10` | 77,92% |
| Regressão Logística | `max_iter = 1000` | 71,07% |

A Árvore de Decisão apresentou a maior acurácia no conjunto de validação e foi selecionada para a avaliação final.

### Avaliação no conjunto de teste

| Modelo | Acurácia |
|---|---:|
| Árvore de Decisão selecionada | **77,92%** |
| `DummyClassifier` (*baseline*) | 68,43% |

O modelo selecionado superou o classificador de referência em **9,49 pontos percentuais**, demonstrando desempenho superior ao de uma estratégia básica de classificação.

Além disso, a acurácia no conjunto de teste ficou acima do objetivo mínimo de 75% estabelecido para o projeto.

## 💡 Principais Conclusões

- A Árvore de Decisão apresentou o melhor desempenho entre os três modelos avaliados.
- A configuração com profundidade 3 obteve a maior acurácia na validação.
- A Floresta Aleatória apresentou desempenho competitivo, mas ligeiramente inferior ao da Árvore de Decisão.
- A Regressão Logística obteve a menor acurácia entre os modelos testados.
- O modelo selecionado alcançou **77,92% de acurácia no conjunto de teste**, superando o objetivo mínimo de 75%.
- A comparação com o `DummyClassifier` demonstrou que o modelo apresentou desempenho superior ao de uma estratégia básica de previsão.


## 👨‍💻 Competências Demonstradas

- Análise exploratória de dados.
- Manipulação de dados com Pandas.
- Preparação de dados para Machine Learning.
- Classificação supervisionada.
- Treinamento e avaliação de modelos preditivos.
- Ajuste e comparação de hiperparâmetros.
- Separação entre conjuntos de treinamento, validação e teste.
- Avaliação de métricas de desempenho.
- Comparação com modelo de referência (*baseline*).
- Interpretação e comunicação de resultados analíticos.  
