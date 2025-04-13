
# Projeto de Regressão: Previsão de Limite de Crédito

Este projeto foi desenvolvido com o objetivo de praticar e entender, na prática, o funcionamento de algoritmos de regressão, especialmente a regressão linear. Ao longo do processo, diferentes estratégias de preparação de dados, geração de dados sintéticos e testes com dados reais foram exploradas, permitindo reflexões sobre os impactos da qualidade dos dados no desempenho dos modelos.

## Estrutura do Projeto

O repositório é composto por cinco notebooks, cada um representando uma etapa do processo de aprendizado:

### `01_dataset_ia_limite_credito.ipynb`
- Utilização de um dataset gerado por IA, com 2 mil registros, sem controle sobre a variabilidade dos dados ou correlação entre variáveis.
- Tentativas de melhorar a performance com engenharia de features e transformação de variáveis.
- Modelos testados: Regressão Linear, Árvore de Regressão, Random Forest e KNN.
- **Resultado:** Baixo desempenho geral (R² ≤ 0.15), indicando problemas na qualidade dos dados.

### `02_dataset_sintetico_controlado.ipynb`
- Geração de um dataset sintético com 5 mil registros e **alta correlação** entre a variável explicativa e o target.
- **Resultado:** Regressão Linear com R² = 0.99, demonstrando o bom funcionamento do modelo em cenário ideal.

### `03_dataset_sintetico_simples.ipynb`
- Geração de um dataset sintético com 2 mil registros **sem controle de correlação**.
- **Resultado:** R² = 0.66. Desempenho razoável, mas limitado pela falta de relação forte entre as variáveis.

### `04_dataset_real_sem_tratamento_outliers.ipynb`
- Utilização de um dataset real com 10.127 registros do Kaggle (fonte abaixo), com tratamento de variáveis categóricas, **sem remoção de outliers**.
- Testes com Regressão Linear, Árvore de Regressão, KNN e Random Forest.
- **Melhor resultado (Random Forest):** R² = 0.59

### `05_dataset_real_com_remocao_outliers.ipynb`
- Mesmo dataset real, com **remoção de outliers**.
- Avaliação do impacto da perda de variabilidade na explicação do target.
- **Melhor resultado (Random Forest):** R² = 0.38
- **Nota:** A regressão linear teve seu R² reduzido de 0.45 para 0.24 após a remoção de outliers, indicando perda de informação relevante.

## Fonte dos Dados Reais

O dataset utilizado nos experimentos 4 e 5 pode ser encontrado no Kaggle:

[Limite de Crédito Bancário – Kaggle](https://www.kaggle.com/datasets/srgiolutzer/limite-de-crdito-bancrio?utm_source=chatgpt.com)

## Lições Aprendidas

- A **qualidade dos dados** é um fator determinante no desempenho dos modelos. Não adianta aplicar algoritmos avançados se os dados não possuem variabilidade ou relação com o target.
- A **remoção de outliers** pode ser prejudicial se feita indiscriminadamente, especialmente em casos onde esses valores ajudam a explicar o comportamento do target.
- A **engenharia de features** pode ser útil, mas só faz diferença quando os dados já possuem alguma estrutura explicativa consistente.
- A **regressão linear funciona muito bem** em cenários com dados controlados e correlação clara, mas seu desempenho real depende do contexto dos dados.

## Próximos Passos (fora do escopo atual)

- Análise de resíduos
- Criação de novas variáveis a partir da base real
- Avaliação de modelos mais complexos com tuning de hiperparâmetros
- Testes de validação cruzada
