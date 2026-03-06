# 🚀 Cripto Data Lakehouse - ELT & Real-Time Analytics

Bem-vindo ao repositório do projeto **Crypto Lakehouse ELT**. Este projeto demonstra a construção de uma arquitetura de dados End-to-End moderna, utilizando o paradigma Data Lakehouse para ingestão, processamento e visualização de dados do mercado de criptomoedas em "Real-Time".

## 🏗️ Arquitetura do Projeto

 <img width="911" height="372" alt="Diagrama Crypto drawio" src="https://github.com/user-attachments/assets/c3799e20-7451-4758-9640-ba3fad511e18" />

O pipeline foi desenhado no modelo **ELT (Extract, Load, Transform)**, garantindo o desacoplamento entre armazenamento e computação.


## 🛠️ Tecnologias Utilizadas
* **Fonte de Dados:** CoinGecko API REST
* **Computação & Orquestração:** Azure Databricks (Workflows)
* **Linguagens:** Python (PySpark) e Spark SQL
* **Armazenamento:** Azure Data Lake Storage Gen2 (ADLS Gen2)
* **Formato de Dados:** Delta Lake (ACID e Time Travel)
* **Visualização de Dados:** Power BI Desktop

## ⚙️ O Pipeline de Dados (Arquitetura Medalhão)

O fluxo de dados segue as melhores práticas da Arquitetura Medalhão, estruturado nas seguintes camadas:

1. **Camada Bronze (Raw):** - Extração de dados da API via Python.
   - Pouso dos dados no formato JSON/bruto diretamento no Data Lake.
   - Realizada uma **Carga Histórica (Full Load)** de 90 dias, seguida por cargas incrementais a cada 3 minutos.

2. **Camada Silver (Cleared):**
   - Leitura da camada Bronze via PySpark.
   - Limpeza de dados, tipagem correta de colunas (cast), tratamento de nulos e deduplicação.
   - Armazenamento otimizado em formato Delta.

3. **Camada Gold (Curated):**
   - Aplicação de regras de negócio em Spark SQL.
   - Cálculo de métricas avançadas: Médias Móveis de 7 dias (SMA), Variação Percentual Diária, Máximas e Mínimas.
   - Criação de uma View dinâmica e leve para consumo direto da ferramenta de BI.

## 📊 Dashboard Executivo

Os dados consolidados são consumidos nativamente pelo Power BI através de um token de acesso seguro (PAT). O painel apresenta:
* Cotação atualizada (Real-Time) das 10 principais criptomoedas.
* Análise de variação Intraday e tendências de longo prazo.
* Interface moderna com UI/UX focada em ambiente corporativo (modo claro, bordas suavizadas e sombras).

<img width="1316" height="725" alt="image" src="https://github.com/user-attachments/assets/fe12eec4-b098-440e-9dc0-9b753bf0eaf6" />

## 🗓️ Jobs

<img width="1902" height="924" alt="img1" src="https://github.com/user-attachments/assets/700f103e-ef60-459d-af0b-2cb2db6cc37e" />
<img width="1713" height="887" alt="img2" src="https://github.com/user-attachments/assets/1578048a-4956-46c0-a53b-5f20abfe1811" />


---
*Desenvolvido por [Arthur Almeida](https://github.com/ArthurrAlmeida)*
