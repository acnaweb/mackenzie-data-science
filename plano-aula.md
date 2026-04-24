# 📅 PLANO DE AULA — Data Science Experience (8 semanas)

## 📊 Dataset Oficial
Telco Customer Churn  
https://www.kaggle.com/datasets/blastchar/telco-customer-churn

---

# 🧠 Estrutura Geral

- Duração: 8 semanas
- Carga por aula: 4h
- Formato:
  - 30% teoria
  - 70% prática
- Projeto contínuo ao longo do curso

---

# 📅 SEMANA 1 — Introdução + Problema de Negócio

## 🎯 Objetivo
Entender o problema de churn e o ciclo de Data Science

## 📚 Conteúdo
- O que é Data Science
- CRISP-DM
- Tipos de problemas
- Contexto de negócio (churn)

## 🛠️ Prática
- Download dataset
- Leitura com pandas
- Visualização inicial

## 📝 Exercícios
1. Qual o problema de negócio?
2. Qual o tipo de problema?
3. Qual a variável target?
4. Quais features parecem relevantes?

## ✅ Gabarito
- Classificação binária
- Target: Churn
- Problema: prever evasão

---

# 📅 SEMANA 2 — EDA

## 🎯 Objetivo
Explorar profundamente os dados

## 📚 Conteúdo
- Estatística descritiva
- Distribuições
- Correlação

## 🛠️ Prática
- Missing values
- Outliers
- Visualizações

## 📝 Exercícios
1. Taxa de churn
2. Relação churn vs tenure
3. Relação churn vs contrato

## ✅ Gabarito
- Churn ~20–30%
- Baixo tenure → alto churn
- Contrato mensal → alto churn

---

# 📅 SEMANA 3 — Estatística Aplicada

## 🎯 Objetivo
Validar hipóteses com dados

## 📚 Conteúdo
- Teste de hipótese
- p-value

## 🛠️ Prática
- Teste entre grupos churn vs não churn

## 📝 Exercícios
1. Monthly charges impacta churn?

## ✅ Gabarito
- p-value < 0.05 → impacto significativo

---

# 📅 SEMANA 4 — Feature Engineering

## 🎯 Objetivo
Preparar dados para ML

## 📚 Conteúdo
- Encoding
- Normalização
- Feature creation

## 🛠️ Prática
- Pipeline com sklearn

## 📝 Exercícios
1. Criar feature avg_ticket
2. Aplicar encoding

## ✅ Gabarito
- avg_ticket melhora modelo

---

# 📅 SEMANA 5 — Modelagem + Escolha de Algoritmos

## 🎯 Objetivo
Construir modelos e escolher corretamente

## 📚 Conteúdo
- Regressão logística
- Árvore
- Random Forest
- Gradient Boosting

---

## 🧠 TABELA DE ALGORITMOS

### 📊 Decisão Rápida

| Cenário | Algoritmo |
|--------|----------|
| Prever churn | Logistic / Random Forest / Boosting |
| Dados tabulares | Gradient Boosting |
| Baseline | Regressão Logística |

---

## 🧠 HEURÍSTICA DE ARQUITETO

1. Comece simples → Logistic Regression  
2. Evolua → Random Forest  
3. Otimize → Gradient Boosting  

---

## 🛠️ Prática
- Treinar 3 modelos

## 📝 Exercícios
1. Qual melhor modelo?
2. Compare resultados

## ✅ Gabarito
- Boosting geralmente melhor

---

# 📅 SEMANA 6 — Avaliação de Modelos

## 🎯 Objetivo
Avaliar corretamente

## 📚 Conteúdo
- Precision / Recall / F1
- ROC-AUC

## 🛠️ Prática
- Comparar métricas

## 📝 Exercícios
1. Qual métrica usar?

## ✅ Gabarito
- Recall (problema de churn)

---

# 📅 SEMANA 7 — AutoML

## 🎯 Objetivo
Automatizar modelagem

## 📚 Conteúdo
- AutoML
- Ferramentas

## 🛠️ Prática
- Rodar AutoML

## 📝 Exercícios
1. AutoML supera modelo manual?

## ✅ Gabarito
- Geralmente sim (performance)

---

# 📅 SEMANA 8 — Projeto Final

## 🎯 Objetivo
Resolver problema completo

## 🛠️ Entrega
- EDA
- Modelo
- Avaliação
- Insights

## 📝 Pergunta chave
Se você fosse o CEO, o que faria com esse modelo?

## ✅ Gabarito esperado
- Reduzir churn com:
  - contratos anuais
  - melhoria suporte
  - retenção de clientes novos

