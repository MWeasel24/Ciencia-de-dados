# Análise Exploratória com PCA e MDS em Vendas de Açougue

## Integrantes

- Daniel Nazário
- Matheus Martins Rodrigues
- Vitor Hugo Trovao De Moraes

## Descrição do Projeto

Este projeto realiza uma análise exploratória de um dataset de vendas de uma rede de açougues utilizando as técnicas PCA e MDS.

O objetivo é reduzir a dimensionalidade dos dados e visualizar possíveis padrões, agrupamentos, proximidades entre produtos e outliers.

## Dataset

Foi utilizado o dataset **Sales at a Chain of Butcher Shops**, disponível no Kaggle:

https://www.kaggle.com/datasets/frrrmin/sales-at-a-chain-of-butcher-shops

O arquivo utilizado contém registros de vendas com informações como:

- data da venda;
- loja;
- produto;
- preço;
- quantidade;
- valor total da venda.

## Técnicas Utilizadas

- Limpeza e preparação dos dados;
- Tratamento de valores ausentes;
- Agregação dos dados por produto;
- Padronização das variáveis numéricas;
- PCA em 2D;
- MDS em 2D;
- Análise de variância explicada;
- Identificação de possíveis outliers.

## Principais Resultados

O PCA indicou que os dois primeiros componentes principais explicaram 77,88% da variância dos dados.

A análise mostrou que:

- o PC1 foi mais influenciado por ticket médio, receita total e quantidade total;
- o PC2 foi mais influenciado pelo preço médio;
- a Arrachera apareceu como possível outlier no PCA;
- o MDS indicou proximidade entre produtos como Chorizo e Pollo.

## Arquivos do Projeto

- `notebook.ipynb`: notebook com o código da análise;
- `README.md`: descrição resumida do projeto;

## Conclusão

As técnicas PCA e MDS ajudaram a visualizar padrões nos dados de vendas do açougue, permitindo identificar produtos com comportamentos semelhantes e produtos com comportamento diferente dos demais.