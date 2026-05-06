# Análise Exploratória com PCA e MDS em Vendas de Açougue

## Explicação detalhada no arquivo "pca_mds_acougue.ipynb"

## Integrantes

- Daniel Nazário
- Matheus Martins Rodrigues
- Vitor Hugo Trovão de Moraes

## Sobre o projeto

Este projeto aplica **PCA** e **MDS** em um dataset de vendas de uma rede de açougues, com o objetivo de identificar padrões, agrupamentos, proximidades entre registros e possíveis outliers.

Como o dataset é propositalmente poluído, foi feita uma etapa de limpeza antes da análise.

## Dataset

Dataset utilizado: **Sales at a Chain of Butcher Shops**  
Link: https://www.kaggle.com/datasets/frrrmin/sales-at-a-chain-of-butcher-shops

Arquivo usado:

- `ventas_carniceria_sucio_4000.csv`

O dataset contém vendas com data, loja, produto, preço, quantidade e valor total da venda.

## Preparação dos dados

Foram feitas as seguintes etapas:

- renomeação das colunas;
- conversão de datas e valores numéricos;
- remoção de valores ausentes;
- remoção de registros inválidos;
- tratamento de outliers pelo método IQR;
- agregação por **Produto** e **Loja**;
- padronização das variáveis numéricas.

Após a limpeza, restaram **3049 registros válidos**. Depois da agregação por produto e loja, foram gerados **30 registros analíticos**.

## Features analisadas

As variáveis usadas foram:

- `numero_vendas`
- `quantidade_total`
- `preco_medio`
- `receita_total`
- `ticket_medio`
- `quantidade_media`
- `variacao_preco`
- `variacao_quantidade`

Essas features foram escolhidas por representarem volume de vendas, faturamento, preço médio, ticket médio e variação das vendas.

## Resultados principais

No PCA, os dois primeiros componentes explicaram **77,39% da variância total**:

- **PC1:** 52,83%
- **PC2:** 24,56%

O **PC1** ficou mais relacionado ao desempenho comercial geral, como receita, quantidade vendida, número de vendas e ticket médio.  
O **PC2** ficou mais associado a diferenças de preço médio e variação nas vendas.

O MDS apresentou uma visualização coerente com o PCA, aproximando registros com comportamentos comerciais semelhantes.

Entre os padrões observados:

- produtos com maior receita e volume de vendas ficaram mais destacados;
- o **Chorizo** apareceu com maior desempenho médio;
- o **Cerdo** apareceu com menor desempenho médio no conjunto limpo;
- alguns registros mais afastados podem indicar possíveis outliers.

## PCA x MDS

O **PCA** foi mais útil para entender quais variáveis mais explicam as diferenças entre os registros e também pode ser usado para redução de features.

O **MDS** foi mais útil para visualizar proximidades entre produtos e lojas, ajudando a identificar registros semelhantes.

## Conclusão

O PCA e o MDS ajudaram a entender melhor o comportamento das vendas. A análise mostrou diferenças entre produtos e lojas, revelou padrões de desempenho comercial e indicou possíveis outliers. Assim, as técnicas foram úteis para transformar um dataset poluído em uma visão mais clara e interpretável.
