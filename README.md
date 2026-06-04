
#  Projeto 27 — Regressão Logística  

![Python](https://img.shields.io/badge/Python-3.11-blue) 
![pandas](https://img.shields.io/badge/pandas-%3E%3D2.2.2-green) 
![numpy](https://img.shields.io/badge/numpy-%3E%3D1.26.4-lightblue) 
![matplotlib](https://img.shields.io/badge/matplotlib-%3E%3D3.9.0-orange) 
![seaborn](https://img.shields.io/badge/seaborn-%3E%3D0.13.2-teal) 
![scikit-learn](https://img.shields.io/badge/scikit--learn-%3E%3D1.5.0-yellow) 
![imbalanced-learn](https://img.shields.io/badge/imbalanced--learn-%3E%3D0.12.2-red) 
![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)

---

## Previsão de Doenças Cardiovasculares

Este projeto tem como objetivo desenvolver um modelo de **Regressão Logística** capaz de prever a presença de doenças cardiovasculares em pacientes, utilizando uma base de dados clínica real.

---

## Tecnologias

- **Python** → análise e manipulação de dados com Pandas, NumPy e visualizações com Matplotlib/Seaborn.   
- **Jupyter Notebook** → ambiente para organizar código e análises passo a passo.  
- **Excel** → base de dados utilizada no projeto.  

---

##  Base de Dados
A base `CARDIO_BASE.csv` contém informações clínicas e hábitos de vida dos pacientes:

- **age** → Idade  
- **gender** → Gênero (1 = masculino, 2 = feminino)  
- **height** → Altura (cm)  
- **weight** → Peso (kg)  
- **cholesterol** → Colesterol (1 = normal, 2 = acima, 3 = muito acima)  
- **gluc** → Glicose (1 = normal, 2 = acima, 3 = muito acima)  
- **smoke** → Tabagismo (1 = sim, 0 = não)  
- **alco** → Consumo de álcool (1 = sim, 0 = não)  
- **active** → Atividade física (1 = sim, 0 = não)  
- **cardio_disease** → Doença cardiovascular (1 = sim, 0 = não) → variável alvo  

---

##  Etapas do Projeto

### 1. Pré-processamento
- Conversão de tipos (`height`, `weight` → float).  
- Tratamento de valores nulos em `weight` (24 registros preenchidos com a média).  
- **[Tratamento de outliers](ca://s?q=Detalhar_tratamento_de_outliers)** em `height` (140–220 cm) e `weight` (40–200 kg).  
- Conversão de variáveis categóricas (`cholesterol`, `gluc`) em dummies.  
- Manutenção das variáveis binárias (`smoke`, `alco`, `active`, `cardio_disease`).  

### 2. Análise Exploratória
- Histogramas para variáveis contínuas (`age`, `height`, `weight`).  
- Gráficos de barras para variáveis categóricas.  
- Matriz de correlação → sem multicolinearidade relevante.  

### 3. Preparação dos Dados
- Separação em treino (70%) e teste (30%), mantendo proporção da variável alvo.  
- Padronização com **StandardScaler**:  
  - Idade (~30–65 anos)  
  - Altura (~140–220 cm)  
  - Peso (~40–200 kg)  
- Verificação de balanceamento da variável alvo → base já equilibrada (~50/50).  

### 4. Treinamento do Modelo
- Modelo de **Regressão Logística** com regularização L2.  
- Intercepto ≈ 0.0356 (sem viés inicial).  
- Principais coeficientes:  
  - `age` → risco aumenta com idade.  
  - `height` → altura maior reduz levemente o risco.  
  - `weight` → peso maior aumenta risco.  

### 5. Avaliação
- Métricas: **accuracy, precision, recall, f1-score**.  
- Relatório de classificação e curva ROC/AUC.  
- Modelo apresentou previsões consistentes e interpretáveis.  

---

##  Conclusão
A limpeza e preparação da base foram essenciais para garantir consistência estatística.  
O modelo de regressão logística mostrou-se adequado para prever doenças cardiovasculares, com resultados robustos e interpretáveis.  

---

##  Exportação da Base Tratada
Após todas as etapas de pré-processamento (remoção de outliers, tratamento de nulos, criação de variáveis dummies e padronização), a base final foi salva em:

**`CARDIO_BASE_TRATADA.csv`**

Esse arquivo representa o dataset pronto para uso em modelos de regressão logística e outras análises.

---

##  Próximos Passos
- Testar outras técnicas de regularização (L1, ElasticNet).  
- Comparar desempenho com outros algoritmos (Random Forest, XGBoost).  
- Explorar feature engineering para variáveis clínicas adicionais.  


##  Autoria
Projeto desenvolvido por **Maria Santos** , como parte da atividade  do curso **Ciências de Dados - EBAC - Módulo 27**.



