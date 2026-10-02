# 📊 Telco Customer Churn Analysis — SQL on Databricks

Análise de evasão de clientes (churn) de uma empresa de telecomunicações  
utilizando **SQL avançado** (CTEs e Window Functions) no **Databricks Serverless**.

---

## 🎯 Objetivo

Identificar os principais segmentos de risco de churn e gerar insights  
acionáveis para times de retenção de clientes.

---

## 🗂️ Dataset

- **Fonte:** [Telco Customer Churn — Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)
- **Volume:** 7.043 clientes | 21 variáveis
- **Taxa de churn geral:** 26,54%

---

## 🛠️ Stack

| Ferramenta | Uso |
|---|---|
| Databricks (Serverless) | Execução das queries |
| Spark SQL | Linguagem de análise |
| GitHub | Versionamento e portfólio |

---

## 💡 Principais Insights

### 1 — Tipo de contrato é o maior preditor de churn
| Contrato | Taxa de Churn |
|---|---|
| Month-to-month | 42,71% 🔴 |
| One year | 11,27% 🟡 |
| Two year | 2,83% 🟢 |

> Clientes mensais cancelam **15x mais** que clientes bianuais.

---

### 2 — Electronic check concentra o maior risco
| Forma de Pagamento | Taxa de Churn |
|---|---|
| Electronic check | 45,29% 🔴 |
| Mailed check | 19,11% 🟡 |
| Bank transfer (automatic) | 16,71% 🟢 |
| Credit card (automatic) | 15,24% 🟢 |

> Pagamentos automáticos têm ~3x menos churn.

---

### 3 — O primeiro ano é crítico
| Tempo de Permanência | Taxa de Churn |
|---|---|
| 0 a 12 meses | 47,44% 🔴 |
| 13 a 24 meses | 28,71% 🟠 |
| 25 a 48 meses | 20,39% 🟡 |
| Mais de 48 meses | 9,51% 🟢 |

> Superar os primeiros 12 meses reduz o risco de churn em 5x.

---

### 4 — Segmento de maior risco identificado (Window Function)
> **Month-to-month + Electronic check = 53,73% de churn**  
> Grupo de intervenção prioritária: 1.850 clientes, 994 em risco.

---

### 5 — O paradoxo da Fibra Ótica
| Serviço | Churn | Ticket Médio |
|---|---|---|
| Fiber optic | 41,89% 🔴 | $91,50 |
| DSL | 18,96% 🟡 | $58,10 |
| Sem internet | 7,40% 🟢 | $21,08 |

> O cliente mais caro é o que mais cancela — sinal de insatisfação  
> com custo-benefício ou maior exposição à concorrência.

## 📁 Estrutura do Projeto

telco-churn-sql-analysis/ │ ├── telco_churn_analysis.sql # Queries completas (CTEs + Window Functions) └── README.md # Documentação e insights


---

## 🧠 Técnicas SQL Utilizadas

- **CTEs** (`WITH`) para modularizar e encadear transformações
- **Window Functions** (`RANK() OVER`, `AVG() OVER`) para rankings e comparações
- **CASE WHEN** para criação de faixas e métricas derivadas
- **CAST** para tratamento de tipos de dados inconsistentes

---


