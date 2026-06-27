# Data 3.4 / DATA1 — Modelagem Preditiva de Vendas para a Big Mart

Este projeto resolve **apenas** o desafio **Data 3.4 / DATA1: Ciência de Dados e Machine Learning**, conforme solicitado no PDF do processo seletivo.

O objetivo é construir uma solução de ciência de dados para prever o volume de vendas (`OutletSales`) de produtos em lojas da Big Mart, utilizando o dataset de treino e teste fornecido.

## Escopo implementado

Foram implementadas somente as exigências principais do desafio:

- carregamento da base de treino e teste;
- preparação e saneamento dos dados;
- tratamento de inconsistências e valores ausentes;
- engenharia de features;
- análise exploratória de dados com visualizações;
- divisão entre treino e validação;
- treinamento de modelos supervisionados de regressão;
- avaliação com métricas de regressão: RMSE, MAE e R²;
- escolha justificada do modelo final;
- geração de predições para a base de teste;
- documentação em Markdown dentro do Notebook.

O desafio extra de aplicação analítica com Streamlit/Dash/Gradio **não foi implementado**.

## Estrutura do projeto

```text
big-mart-data1-core/
├── data/
│   └── raw/
│       ├── train.csv
│       └── test.csv
├── notebooks/
│   └── data1-big-mart-sales-core.ipynb
├── outputs/
│   ├── figures/
│   └── models/
├── requirements.txt
```

## Como executar

1. Crie e ative um ambiente virtual:

```bash
python -m venv .venv
```

Windows:

```bash
.venv\Scripts\activate
```

Linux/Mac:

```bash
source .venv/bin/activate
```

2. Instale as dependências:

```bash
pip install -r requirements.txt
```

3. Abra o Jupyter Notebook:

```bash
jupyter notebook notebooks/data1-big-mart-sales-core.ipynb
```

4. Execute as células em ordem.

O Notebook foi configurado para localizar os arquivos automaticamente tanto quando executado a partir da raiz do projeto quanto a partir da pasta `notebooks/`.

## Arquivos de dados esperados

Os arquivos devem estar em:

```text
data/raw/train.csv
data/raw/test.csv
```

Eles já foram incluídos nesta estrutura de projeto.

## Saídas geradas pelo Notebook

Durante a execução, o Notebook gera:

- gráficos em `outputs/figures/`;
- modelo treinado em `outputs/models/big_mart_model.joblib`;
- arquivo de predições em `outputs/big_mart_test_predictions.csv`.

## Observações metodológicas

A solução utiliza pipelines do Scikit-Learn para reduzir risco de vazamento de dados. As transformações são ajustadas apenas sobre os dados de treino e aplicadas posteriormente à validação e ao teste.

As variáveis categóricas são codificadas com One-Hot Encoding. As variáveis numéricas recebem imputação por mediana. O modelo final é escolhido com base no menor RMSE na base de validação, considerando também MAE e R².



