# Consolidação de Medalhas Olímpicas (Data Lake)

## Dados utilizados

**Dados históricos (1896–2022):**
Base dos Dados – Histórico das Olimpíadas

https://basedosdados.org/dataset/62f8cb83-ac37-48be-874b-b94dd92d3e2b

**Dados Paris 2024:**
Kaggle – Paris 2024 Olympic Summer Games

https://www.kaggle.com/datasets/piterfm/paris-2024-olympic-summer-games/data

## Descrição

Este trabalho implementa um **Data Lake local** para ingestão, tratamento, integração e análise de dados olímpicos, combinando informações históricas (1896–2022) com dados dos Jogos Olímpicos de Paris 2024.

Os dados são organizados em camadas (**RAW, BRONZE e GOLD**), permitindo rastreabilidade, padronização e geração de análises consolidadas.

## Processos

### 🔹 Camada RAW

* Armazenamento dos dados brutos
* Criação automática de metadados JSON para cada dataset

### 🔹 Camada BRONZE

* Padronização dos dados (colunas e formatos)
* Integração entre dados históricos e 2024
* Conversão de arquivos CSV para Parquet
* Criação de datasets enriquecidos (JOINs)

### 🔹 Camada GOLD

#### 🥇 Análise de Medalhas

* Consolidação do total de medalhas por país
* Ranking dos países com melhor desempenho

#### 🏅 Análise de Modalidades

* Identificação das modalidades mais frequentes
* Ranking dos esportes com maior ocorrência

#### 👥 Análise de Gênero

* Distribuição de atletas por sexo

### 🔹 Catálogo de Dados

* Geração automática do arquivo `metadata_schema.json`
* Organização dos datasets por camada (RAW, BRONZE, GOLD)
* Registro de campos, descrições e caminhos dos dados

## Estrutura do Projeto

```
olympics-datalake/
│
├── raw/        # Dados brutos + metadata
├── bronze/     # Dados tratados (Parquet)
├── gold/       # Análises e visualizações
│
└── metadata_schema.json  # Catálogo do Data Lake
```
