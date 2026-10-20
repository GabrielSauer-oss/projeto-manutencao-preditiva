Predição de Falhas em Máquinas Industriais com Machine Learning

1. Objetivo

Desenvolver modelos de aprendizado de máquina supervisionado para identificar falhas em máquinas industriais com base em variáveis operacionais, contribuindo para estudos de manutenção preditiva.

2. Dataset

Foi utilizado o AI4I 2020 Predictive Maintenance Dataset, disponível publicamente no UCI Machine Learning Repository.

Fonte: https://archive.ics.uci.edu/dataset/601/ai4i+2020+predictive+maintenance+dataset

- Registros: 10.000.
- Colunas: 12.
- Variável-alvo: `Machine failure`.
- Registros sem falha: 9.661 (96,61%).
- Registros com falha: 339 (3,39%).

O conjunto de dados é sintético e foi desenvolvido para estudos de manutenção preditiva.

3. Metodologia

O projeto foi desenvolvido em Python no Google Colab, utilizando Pandas, Scikit-learn, Matplotlib e Seaborn.

Etapas realizadas:

1. Carregamento e análise exploratória dos dados.
2. Verificação de valores ausentes, duplicatas e distribuição das classes.
3. Seleção das variáveis de entrada e da variável-alvo.
4. Divisão dos dados em treinamento (80%) e teste (20%), com estratificação.
5. Pré-processamento das variáveis numéricas e categóricas.
6. Treinamento e comparação dos modelos.
7. Busca de hiperparâmetros com validação cruzada estratificada em cinco partes.
8. Avaliação com acurácia, precisão, recall, F1-score, Average Precision e matrizes de confusão.

Foram avaliados Regressão Logística, Árvore de Decisão e Random Forest, além de um modelo baseline inicial. As variáveis indicadoras de tipos específicos de falha foram excluídas das entradas para evitar vazamento de informações.

4. Resultados

Resultados dos modelos após o ajuste de hiperparâmetros:

| Modelo | Acurácia | Precisão | Recall | F1-score | AP |
|---|---:|---:|---:|---:|---:|
| Regressão Logística | 82,3% | 13,9% | 80,9% | 23,7% | 38,0% |
| Árvore de Decisão | 96,1% | 45,7% | 77,9% | 57,6% | 69,2% |
| Random Forest | 98,3% | 81,5% | 64,7% | 72,1% | 80,4% |

A Random Forest apresentou o melhor F1-score e a maior Average Precision, além da maior precisão. A Árvore de Decisão apresentou recall superior ao da Random Forest, enquanto a Regressão Logística identificou mais falhas, mas gerou muitos alarmes falsos.

A Random Forest foi selecionada como candidata ao modelo final considerando o equilíbrio entre precisão e recall.

5. Limitações

- O conjunto de dados é sintético e pode não representar integralmente uma fábrica real.
- A baixa proporção de falhas torna a acurácia insuficiente como única métrica.
- Os resultados dependem dos dados e das configurações utilizadas.
- É necessária validação com dados industriais reais antes de qualquer aplicação operacional.

6. Conclusão

O projeto demonstrou a aplicação de aprendizado de máquina supervisionado em um problema de manutenção preditiva. A comparação evidenciou que a Random Forest apresentou o melhor F1-score e Average Precision, enquanto a Árvore de Decisão obteve maior recall que esse modelo.

A escolha final deve considerar o custo das falhas não detectadas e dos alarmes falsos. Os resultados são promissores para fins acadêmicos, mas não garantem o mesmo desempenho em ambientes industriais reais.

7. Arquivos

O notebook Jupyter (`.ipynb`) contém o código, o treinamento dos modelos e a avaliação experimental do projeto.

8. Tecnologias utilizadas

- Python
- Google Colab
- Pandas
- Scikit-learn
- Matplotlib
- Seaborn
- UCI Machine Learning Repository
