# Análise de Acessos por Velocidade Contratada – Banda Larga Fixa (2020)

Este projeto apresenta uma exploração estatística dos dados de internet banda larga fixa no Brasil durante o segundo trimestre de 2020.

## Sobre o Dataset
- **Fonte:** Anatel (Portal de Dados Abertos do Governo Federal).
- **Finalidade:** Analisar a infraestrutura de rede e a qualidade das conexões oferecidas no país.
- **Volume:** 375.008 registros com 10 variáveis principais (Razão Social, CNPJ, UF, Velocidade, Acessos, etc).
- https://dados.gov.br/dados/conjuntos-dados/acessos-por-velocidade-contratada-banda-larga-fixa

## O que foi feito
1. **Tratamento de Dados:** Limpeza de valores nulos, correção de tipagem e conversão de unidades (Kbps para Mbps) para garantir a precisão da análise.
2. **Exploração Estatística:** Cálculo de medidas de tendência central (Média, Mediana, Moda) e dispersão (Desvio Padrão, Variância, Quartis e IQR).
3. **Visualização de Dados:** Geração de Histograma, Boxplot, Gráfico de Dispersão e Gráfico de Barra (Observar o total de acessos por unidade federativa).

## Principais Insights
- **Desigualdade Digital:** Enquanto a média de velocidade era de 36 Mbps, a mediana era de apenas 8 Mbps, indicando que metade das conexões no país eram limitadas.
- **Pequenos Provedores:** O mercado brasileiro possui uma forte presença de provedores regionais com poucos acessos por registro, contrastando com grandes operadoras que concentram centenas de milhares de usuários.
- **Impacto da Época:** Os dados refletem o gargalo tecnológico enfrentado pelos brasileiros no início do isolamento social em 2020.

## Tecnologias Utilizadas
- Python
- Pandas & Numpy (Cálculos estatísticos)
- Matplotlib & Seaborn (Visualização de dados)
- Jupyter Notebook
