# Análise Exploratória com PCA e MDS em Vendas de Açougue

## Integrantes

- Daniel Nazário
- Matheus Martins Rodrigues
- Vitor Hugo Trovão de Moraes

## Descrição do projeto

Este projeto realiza uma análise exploratória em um dataset de vendas de uma rede de açougues utilizando as técnicas **PCA** (*Principal Component Analysis*) e **MDS** (*Multidimensional Scaling*).

O objetivo principal não é apenas reduzir a quantidade de variáveis, mas compreender melhor o comportamento dos dados, investigando padrões de venda, proximidades entre registros, possíveis agrupamentos e outliers.

Como o dataset foi disponibilizado de forma propositalmente poluída, também foi realizada uma etapa de limpeza e preparação dos dados antes da aplicação das técnicas de redução dimensional.

## Dataset utilizado

Foi utilizado o dataset **Sales at a Chain of Butcher Shops**, disponível no Kaggle:

https://www.kaggle.com/datasets/frrrmin/sales-at-a-chain-of-butcher-shops

O arquivo utilizado foi:

- `ventas_carniceria_sucio_4000.csv`

O dataset contém registros de vendas de uma rede de açougues, com informações como:

- data da venda;
- loja;
- produto;
- preço;
- quantidade vendida;
- valor total da venda.

## Problema investigado

A análise buscou entender se diferentes produtos e lojas apresentam comportamentos parecidos ou diferentes em relação às vendas. Para isso, foram criados indicadores numéricos capazes de resumir o desempenho comercial dos produtos em cada loja.

A pergunta central do projeto foi:

> É possível identificar padrões, semelhanças, agrupamentos ou outliers nas vendas dos produtos a partir de variáveis como preço, quantidade, receita e ticket médio?

## Preparação dos dados

Foram realizadas as seguintes etapas de preparação:

- renomeação das colunas para facilitar a leitura;
- conversão de datas e variáveis numéricas;
- remoção de valores ausentes;
- remoção de registros inválidos, como preços, quantidades ou vendas totais menores ou iguais a zero;
- remoção de outliers extremos pelo método do intervalo interquartil (IQR);
- agregação dos dados por **Produto** e **Loja**;
- criação de features numéricas para análise;
- padronização dos dados com `StandardScaler`.

Após a limpeza, o dataset ficou com **3049 registros válidos**. Em seguida, os dados foram agregados por produto e loja, formando **30 registros analíticos** para aplicação do PCA e do MDS.

## Features selecionadas

As features usadas na análise foram:

- `numero_vendas`: quantidade de vendas registradas;
- `quantidade_total`: soma total da quantidade vendida;
- `preco_medio`: preço médio do produto;
- `receita_total`: soma total das vendas;
- `ticket_medio`: valor médio por venda;
- `quantidade_media`: quantidade média vendida por venda;
- `variacao_preco`: desvio padrão do preço;
- `variacao_quantidade`: desvio padrão da quantidade vendida.

Essas variáveis foram escolhidas porque representam diferentes aspectos do comportamento comercial dos produtos, como volume de vendas, faturamento, preço, ticket médio e variação nas vendas.

## Técnicas utilizadas

### PCA

O PCA foi utilizado para transformar as variáveis originais em componentes principais, preservando a maior parte possível da variância dos dados. Com isso, foi possível visualizar os registros em duas dimensões e analisar quais variáveis mais influenciaram os principais eixos da projeção.

### MDS

O MDS foi utilizado para representar visualmente a similaridade entre os registros. Diferente do PCA, o MDS busca preservar as distâncias entre os pontos, permitindo observar quais combinações de produto e loja possuem comportamentos de venda mais parecidos.

## Principais resultados

No PCA, os dois primeiros componentes principais explicaram aproximadamente **77,39% da variância total dos dados**:

- **PC1:** 52,83%;
- **PC2:** 24,56%.

Esse resultado indica que a visualização em 2D foi suficiente para representar boa parte da estrutura dos dados.

A análise mostrou que:

- o **PC1** está mais associado ao desempenho comercial geral, como receita total, número de vendas, quantidade vendida e ticket médio;
- o **PC2** está mais relacionado às diferenças de preço médio e variação nas vendas;
- produtos com maior volume de vendas e maior receita ficaram mais distantes dos produtos com menor desempenho;
- o **Chorizo** apareceu como um dos produtos de maior desempenho médio;
- o **Cerdo** apareceu com menor desempenho médio no conjunto limpo;
- o MDS apresentou uma organização visual coerente com o PCA, aproximando registros com comportamento comercial semelhante;
- alguns pontos mais afastados podem ser interpretados como possíveis outliers, geralmente ligados a combinações de produto e loja com receita, ticket ou volume de vendas acima ou abaixo do padrão.

## Comparação entre PCA e MDS

O PCA e o MDS apresentaram resultados complementares.

O **PCA** foi mais útil para entender quais variáveis explicam melhor as diferenças entre os registros. Ele também pode ser usado para redução de features, já que os primeiros componentes concentram grande parte da variância dos dados.

O **MDS** foi mais útil para visualizar proximidades entre registros. Ele ajudou a observar quais produtos e lojas possuem comportamentos semelhantes, mas não é a técnica mais indicada para redução de features em modelos preditivos.

De forma geral, os padrões observados no MDS foram coerentes com os padrões encontrados no PCA.

## Arquivos do projeto

- `Trabalho_PCAeMDS_corrigido_completo.ipynb`: notebook completo com limpeza, PCA, MDS, gráficos e interpretações;
- `ventas_carniceria_sucio_4000.csv`: dataset utilizado na análise;
- `Relatorio_PCA_MDS_Carniceria.docx`: relatório curto com as descobertas do projeto;
- `README.md`: descrição resumida do projeto.

## Conclusão

As técnicas PCA e MDS ajudaram a compreender melhor o dataset de vendas da rede de açougues. O PCA mostrou que grande parte da variação dos dados pode ser explicada por poucos componentes, principalmente ligados ao desempenho comercial dos produtos. Já o MDS ajudou a visualizar proximidades e diferenças entre combinações de produto e loja.

A análise permitiu identificar padrões de vendas, produtos com comportamentos semelhantes e possíveis outliers. Portanto, os métodos foram úteis como ferramentas de análise exploratória e ajudaram a transformar um dataset poluído em uma visão mais clara sobre o comportamento das vendas.
