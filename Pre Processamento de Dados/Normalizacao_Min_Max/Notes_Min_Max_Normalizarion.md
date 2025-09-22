# 📘 Estudos sobre Normalização Min-Max

## 📌 1. O que é Normalização Min-Max?
A **normalização Min-Max** é uma técnica de escalonamento que transforma os valores de um atributo para um intervalo fixo, geralmente **[0, 1]**.  

👉 Exemplo: Se você tem notas variando de 0 a 100, pode normalizá-las para que todas fiquem entre 0 e 1.

- A normalização ajuda algoritmos que dependem de métricas de distância, como: KNN e SVM. Essa técnica evita que os valores maiores atrapalhem na aprendizagem.
  
### 📌 Normalização e Outliers

A **normalização** ajuda algoritmos que dependem de **métricas de distância**, como **KNN** e **SVM**.  
Essa técnica evita que os valores maiores atrapalhem na aprendizagem.

---

#### ⚠️ CUIDADO

Sempre preste atenção aos **outliers**, porque eles tendem a **espremer os valores para perto de 0**.



### ❓ O que devemos fazer com o outlier?

Primeiro, verificamos a importância do outlier para o **dataset** e podemos tomar dois caminhos após isso:

### 🔧 Tratar o outlier
1. **Remoção** → se o outlier for um erro de coleta ou não fizer sentido no contexto, pode ser removido.  
2. **Substituição** → trocar o outlier por **média**, **mediana** ou **interpolação**.  

### 📊 Usar outra métrica de *Feature Scaling* (Escalonamento)
1. **Z-Score Normalization (StandardScaler)**  
2. **RobustScaler**


---

## 🧮 2. Fórmula
A fórmula é:  

X_{normalizado} = X - Xmin/Xmax - Xmin

- **X** → valor original  
- **Xmin** → valor mínimo da variável  
- **Xmax** → valor máximo da variável  
- **Xnormalizado** → valor resultante (entre 0 e 1)  

---

## 🎯 3. Intuição da Transformação
- Se (X = Xmin) → resultado será **0**  
- Se (X = Xmax) → resultado será **1**  
- Valores intermediários ficam **proporcionalmente** entre 0 e 1  

👉 A técnica **preserva a distribuição original**, só muda a escala.

---

## 📊 4. Exemplo Matemático
Conjunto de dados:  

\[
[10, 20, 30, 40, 50]
\]  

- \(X_{min} = 10\)  
- \(X_{max} = 50\)  

Cálculo:  
- 10 → (10−10)/(50−10) = **0.0**  
- 20 → (20−10)/40 = **0.25**  
- 30 → (30−10)/40 = **0.5**  
- 40 → (40−10)/40 = **0.75**  
- 50 → (50−10)/40 = **1.0**  

👉 Resultado final: **[0.0, 0.25, 0.5, 0.75, 1.0]**

---

## 💻 5. Exemplo em Python
```python
from sklearn.preprocessing import MinMaxScaler
import numpy as np

# Dados originais
dados = np.array([[10], [20], [30], [40], [50]])

# Criando o objeto MinMaxScaler
scaler = MinMaxScaler()

# Ajustando e transformando os dados
dados_normalizados = scaler.fit_transform(dados)

print(dados_normalizados)
