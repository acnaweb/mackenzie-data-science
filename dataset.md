# 📊 DATASET — Telco Customer Churn

## 🔗 Fonte Oficial (Kaggle)

https://www.kaggle.com/datasets/blastchar/telco-customer-churn

---

## 🎯 Contexto de Negócio

Uma empresa de telecomunicações deseja prever quais clientes têm maior probabilidade de cancelar seus serviços (**churn**), permitindo ações preventivas de retenção.

---

## 📁 Arquivo Principal

WA_Fn-UseC_-Telco-Customer-Churn.csv

---

## 📊 Dicionário de Dados

| Coluna | Tipo | Descrição |
|--------|------|----------|
| customerID | string | Identificador do cliente |
| gender | categórico | Masculino / Feminino |
| SeniorCitizen | binário | Cliente idoso (0/1) |
| Partner | categórico | Possui parceiro |
| Dependents | categórico | Possui dependentes |
| tenure | numérico | Tempo como cliente (meses) |
| PhoneService | categórico | Possui telefone |
| MultipleLines | categórico | Múltiplas linhas |
| InternetService | categórico | Tipo de internet |
| OnlineSecurity | categórico | Segurança online |
| OnlineBackup | categórico | Backup online |
| DeviceProtection | categórico | Proteção de dispositivo |
| TechSupport | categórico | Suporte técnico |
| StreamingTV | categórico | Streaming TV |
| StreamingMovies | categórico | Streaming filmes |
| Contract | categórico | Tipo de contrato |
| PaperlessBilling | categórico | Fatura digital |
| PaymentMethod | categórico | Forma de pagamento |
| MonthlyCharges | numérico | Valor mensal |
| TotalCharges | numérico (string) | Valor total pago |
| Churn | binário | Cliente cancelou (Yes/No) |

---

## ⚠️ Problemas Reais do Dataset (IMPORTANTE PARA AULA)

Este dataset é excelente porque contém problemas reais de produção:

### 1. Tipo incorreto
- `TotalCharges` está como string

### 2. Valores ausentes
- Registros com espaço vazio (" ")

### 3. Variáveis categóricas
- Necessário encoding

### 4. Classe desbalanceada
- Churn ~26%

---

## 🧹 Versão Preparada (Para Aula)

### 🔧 Regras de limpeza

- Converter `TotalCharges` → float
- Remover linhas nulas
- Remover `customerID`
- Converter target:
  - Yes → 1
  - No → 0

---

## 🧪 Código de Preparação (Base Oficial)

```python
import pandas as pd

df = pd.read_csv("Telco-Customer-Churn.csv")

# Corrigir tipo
df['TotalCharges'] = pd.to_numeric(df['TotalCharges'], errors='coerce')

# Remover nulos
df = df.dropna()

# Remover ID
df = df.drop(columns=['customerID'])

# Converter target
df['Churn'] = df['Churn'].map({'Yes': 1, 'No': 0})

df.head()
