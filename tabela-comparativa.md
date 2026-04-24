# 🧠 Tabela Profissional de Algoritmos de Machine Learning

## 1. Tabela Geral

| Algoritmo | Categoria | Tipo de Problema | Quando Utilizar | Pontos Fortes | Limitações |
|---|---|---|---|---|---|
| Regressão Linear | Supervisionado | Regressão | Prever valores contínuos com relação linear | Simples e interpretável | Não captura relações complexas |
| Regressão Logística | Supervisionado | Classificação | Baseline para problemas binários, como churn | Rápida e explicável | Pode performar mal em relações não lineares |
| Árvore de Decisão | Supervisionado | Classificação / Regressão | Quando o problema pode ser explicado por regras | Fácil de interpretar | Alto risco de overfitting |
| Random Forest | Supervisionado | Classificação / Regressão | Quando se busca robustez e bom desempenho geral | Reduz overfitting das árvores | Menos interpretável |
| Gradient Boosting | Supervisionado | Classificação / Regressão | Dados tabulares com necessidade de alta performance | Excelente desempenho | Requer ajuste fino |
| XGBoost | Supervisionado | Classificação / Regressão | Competição, crédito, churn, risco, fraude | Alta performance | Mais complexo |
| LightGBM | Supervisionado | Classificação / Regressão | Grandes volumes de dados tabulares | Muito rápido | Pode ser sensível a parâmetros |
| SVM | Supervisionado | Classificação | Dados menores com separação clara entre classes | Bom em alta dimensão | Escala mal em grandes bases |
| KNN | Supervisionado | Classificação / Regressão | Problemas baseados em similaridade | Simples | Lento em bases grandes |
| Naive Bayes | Supervisionado | Classificação | Texto, spam, classificação probabilística | Muito rápido | Assume independência entre variáveis |
| K-Means | Não supervisionado | Clusterização | Segmentação de clientes ou grupos semelhantes | Simples e rápido | Precisa definir número de clusters |
| Hierarchical Clustering | Não supervisionado | Clusterização | Quando se deseja hierarquia entre grupos | Fácil de visualizar | Escala mal |
| DBSCAN | Não supervisionado | Clusterização / Anomalia | Detectar grupos e ruídos | Não exige número fixo de clusters | Sensível a parâmetros |
| PCA | Não supervisionado | Redução de dimensionalidade | Reduzir número de variáveis | Ajuda visualização e performance | Perde interpretabilidade |
| Isolation Forest | Não supervisionado | Detecção de anomalia | Fraude, outliers, comportamento incomum | Eficiente para anomalias | Pode exigir ajuste cuidadoso |

---

## 2. Tabela Decisão Rápida

| Cenário | Algoritmos Recomendados |
|---|---|
| Prever churn | Regressão Logística, Random Forest, XGBoost, LightGBM |
| Prever vendas ou receita | Regressão Linear, Random Forest Regressor, Gradient Boosting |
| Score de crédito | Regressão Logística, XGBoost, LightGBM |
| Detecção de fraude | Random Forest, XGBoost, Isolation Forest |
| Segmentação de clientes | K-Means, Hierarchical Clustering |
| Redução de variáveis | PCA |
| Classificação de texto | Naive Bayes, Logistic Regression |
| Dados tabulares corporativos | Gradient Boosting, XGBoost, LightGBM |
| Modelo explicável para negócio | Regressão Logística, Árvore de Decisão |
| Baseline rápido | Regressão Logística ou Regressão Linear |
| Modelo com alta performance | XGBoost ou LightGBM |

---

## 3. Heurística de Arquiteto

### Regra prática para projetos reais

1. **Comece simples**
   - Use Regressão Linear para regressão.
   - Use Regressão Logística para classificação.

2. **Crie um baseline confiável**
   - Avalie rapidamente se os dados têm sinal preditivo.
   - Não comece com modelos complexos.

3. **Evolua para modelos robustos**
   - Use Random Forest para capturar relações não lineares.
   - Compare com o baseline.

4. **Otimize performance**
   - Use Gradient Boosting, XGBoost ou LightGBM.
   - Ajuste hiperparâmetros.
   - Compare métricas relevantes ao negócio.

5. **Escolha métrica pelo impacto de negócio**
   - Churn: Recall e F1-score.
   - Fraude: Recall e Precision.
   - Crédito: ROC-AUC, KS, Precision/Recall.
   - Vendas: MAE, RMSE, MAPE.

6. **Não escolha modelo só por métrica**
   - Considere explicabilidade.
   - Considere custo operacional.
   - Considere manutenção.
   - Considere risco regulatório.

---

## 4. Heurística para Churn

### Problema
Prever clientes com risco de cancelamento.

### Modelos sugeridos

| Etapa | Modelo | Objetivo |
|---|---|---|
| Baseline | Regressão Logística | Criar referência simples e explicável |
| Evolução | Random Forest | Capturar relações não lineares |
| Alta performance | XGBoost / LightGBM | Maximizar resultado preditivo |
| Explicabilidade | SHAP | Explicar fatores de churn |

### Métrica prioritária

Para churn, normalmente o foco principal é **Recall**, porque o maior risco é deixar de identificar clientes que realmente vão cancelar.

---

## 5. Erros Comuns

| Erro | Consequência |
|---|---|
| Escolher algoritmo antes de entender o problema | Modelo tecnicamente bom, mas inútil para o negócio |
| Usar accuracy em dataset desbalanceado | Métrica enganosa |
| Ignorar feature engineering | Perda de performance |
| Não separar treino e teste corretamente | Vazamento de dados |
| Usar modelo complexo sem baseline | Dificuldade de explicar ganho real |
| Não interpretar o modelo | Baixa adoção pelo negócio |
| Não transformar variável categórica | Erro no treinamento |
| Não tratar valores ausentes | Falha no pipeline |
| Não medir impacto de negócio | Projeto vira apenas exercício técnico |

---

## 6. Frase-chave para Aula

> Em projetos reais de Data Science, o melhor modelo não é apenas o que tem maior métrica.  
> É o modelo que resolve o problema de negócio, é compreensível, sustentável e acionável.

---

## 7. Aplicação no Projeto Telco Churn

Para o dataset Telco Customer Churn, a recomendação didática é:

1. Começar com **Regressão Logística**
2. Comparar com **Árvore de Decisão**
3. Evoluir para **Random Forest**
4. Opcionalmente testar **XGBoost ou LightGBM**
5. Explicar as principais variáveis:
   - tenure
   - Contract
   - MonthlyCharges
   - TechSupport
   - InternetService
6. Traduzir o modelo em ações:
   - retenção de clientes novos
   - incentivo a contratos anuais
   - melhoria no suporte técnico
   - ofertas para clientes de alto risco
