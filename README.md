# 🍦 Prevendo Vendas de Sorvetes com Machine Learning (AutoML Azure)

Este projeto faz parte do desafio da **Digital Innovation One (DIO)** sobre Machine Learning na nuvem.  
O objetivo é aplicar conceitos fundamentais de aprendizado de máquina para prever **vendas de sorvete com base na temperatura do dia**, utilizando o **Azure Machine Learning Studio** com **AutoML**.

---

## 📍 Cenário

Imagine que você é proprietário de uma sorveteria chamada **Gelato Mágico**, localizada em uma cidade litorânea.  
A quantidade de sorvetes vendidos diariamente apresenta forte correlação com a temperatura ambiente.  
Com o uso de Machine Learning, é possível prever a demanda e otimizar a produção — evitando desperdícios e falta de produto.

---

## 🎯 Objetivo

Desenvolver um **modelo de regressão preditiva** capaz de:
- Prever o número de sorvetes vendidos com base na temperatura diária;
- Reduzir perdas e melhorar o planejamento de produção;
- Automatizar o processo de previsão com um endpoint em tempo real no Azure.

---

## 🧰 Tecnologias e Ferramentas Utilizadas

- **Azure Machine Learning Studio**
- **AutoML (Automated Machine Learning)**
- **Python / Scikit-learn**
- **ElasticNet Regression**
- **MaxAbsScaler (normalização dos dados)**
- **MLflow (registro de experimentos)**
- **REST Endpoint do Azure**

---

## 📊 Dataset Utilizado

O dataset contém 200 registros simulados com as seguintes colunas:
- **Dia** → (inteiro sequencial)
- **Temperatura (°C)** → (variável independente)
- **QtdeVendida** → (variável dependente, alvo de previsão)

Arquivo: `inputs/dataset_icecream.csv`

---

## ⚙️ Processo do Experimento

1. Criação do workspace no Azure Machine Learning: `ML-Dio-proj1`
2. Upload do dataset “Arquivo-Sorvete-4:1”
3. Execução de experimento automático com vários algoritmos de regressão
4. Identificação do melhor modelo: **MaxAbsScaler + ElasticNet**
5. Registro das métricas e implantação em endpoint REST

📸 *Prints do processo (Azure Machine Learning Studio):*
- Criação do Workspace: 

<img width="1418" height="890" alt="image" src="https://github.com/user-attachments/assets/5673896a-a64f-4943-9f35-e1fa06bcecd5" />


- Execução do Experimento AutoML: 

<img width="1418" height="890" alt="image" src="https://github.com/user-attachments/assets/a28f9c9d-b156-4ba5-a298-2edac63037e3" />


- Resumo do Modelo: 

<img width="1418" height="890" alt="image" src="https://github.com/user-attachments/assets/89c169f1-c523-4362-9044-192182f8cf66" />


- Métricas Detalhadas: 

<img width="652" height="839" alt="image" src="https://github.com/user-attachments/assets/a16e988e-db60-4481-bab0-df6c18dd1e0b" />


- Hiperparâmetros do Treinamento: 

<img width="652" height="839" alt="image" src="https://github.com/user-attachments/assets/7b9d76c9-0534-4742-bac7-46a7dc3a7ba0" />


- Implantação do Modelo: 

<img width="1424" height="839" alt="image" src="https://github.com/user-attachments/assets/99815890-47e1-4509-8a82-0f35c977ccc6" />


- Ponto de Extremidade REST: 

<img width="1424" height="839" alt="image" src="https://github.com/user-attachments/assets/4e878564-fe9a-4510-8a70-269332f1230f" />


---

## 🧠 Melhor Modelo Identificado

### **MaxAbsScaler + ElasticNet Regression**

| Métrica | Valor |
|----------|--------|
| RMSE (Erro de quadrado médio normalizado) | **0.06901** |
| R² (Coeficiente de determinação) | **0.90555** |
| Variância Explicada | **0.91423** |
| Erro absoluto médio | **7.9668** |
| Erro percentual médio | **4.4066%** |
| Correlação de Spearman | **0.94005** |

📸 Print de métricas detalhadas:  

<img width="645" height="839" alt="image" src="https://github.com/user-attachments/assets/0f59d1d6-c056-4068-9cef-0689e5f6eb1f" />


---

## 🔬 Hiperparâmetros do Modelo

```json
{
  "class_name": "ElasticNet",
  "module": "sklearn.linear_model",
  "param_kwargs": {
    "alpha": 0.001,
    "l1_ratio": 0.8436842105263158
  }
}
