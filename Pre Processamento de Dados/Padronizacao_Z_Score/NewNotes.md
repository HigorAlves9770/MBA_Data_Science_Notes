# 📘 Estudos sobre Z-Score ou Standardization (Gaussiana)

---

## 📌 1. Distribuição Normal ou Gaussiana

A **distribuição normal**, também chamada de **distribuição gaussiana**, é uma das distribuições de probabilidade mais importantes em estatística e machine learning.  
Ela descreve dados que se concentram em torno de uma **média**, formando o clássico **"sino"** quando representada graficamente.

- **μ (média)** → valor médio  
- **σ (desvio padrão)** → medida da dispersão dos dados  

---

## 📊 2. Características Principais

✔️ **Simétrica** em torno da média (μ)  
✔️ **Média (μ)**, **mediana** e **moda** são iguais  
✔️ A maioria dos valores está próxima da média; valores extremos são raros  
✔️ Os **desvios-padrão (σ)** determinam a dispersão:

- ~68% dos dados estão dentro de **1σ** da média  
- ~95% estão dentro de **2σ**  
- ~99,7% estão dentro de **3σ**  
  _(Regra Empírica ou 68-95-99,7)_

---

## 🧮 3. Função de Densidade de Probabilidade (PDF)

A fórmula da **PDF** da distribuição normal é:

\[
f(x) = \frac{1}{\sigma \sqrt{2\pi}} e^{ -\frac{(x - \mu)^2}{2\sigma^2} }
\]

- **x** → valor da variável aleatória  
- **μ** → média da distribuição  
- **σ** → desvio padrão  
- **e** → base do logaritmo natural (~2,718)

---

## 🎯 4. Intuição

- Valores **próximos à média** têm maior probabilidade  
- Valores **longe da média** são raros  
- A forma da curva é de **sino**, refletindo a frequência dos valores  

---

# 📐 Cálculo do Desvio Padrão

O **desvio padrão** é uma medida estatística que mostra o quanto os dados estão espalhados em relação à média.

---

## 📌 Conceitos Importantes

- **Média** → valor central do conjunto de dados  
- **Variância** → média dos quadrados das diferenças entre cada valor e a média  
- **Desvio padrão** → raiz quadrada da variância  

---

## 📝 Passo a Passo do Cálculo

1️⃣ Calcular a média dos dados  
2️⃣ Subtrair cada valor pela média (diferença)  
3️⃣ Elevar cada diferença ao quadrado  
4️⃣ Calcular a média dos quadrados → **variância**  
5️⃣ Tirar a raiz quadrada da variância → **desvio padrão**

---

## 📊 Exemplo Prático

Dados: **4, 6, 8, 10**

**Passo 1: Média**  

[4 + 6 + 8 + 10] = 7


**Passo 2: Diferença de cada valor para a média**  
- 4 - 7 = -3  
- 6 - 7 = -1  
- 8 - 7 = 1  
- 10 - 7 = 3  

**Passo 3: Quadrado das diferenças**  
- (-3)² = 9  
- (-1)² = 1  
- 1² = 1  
- 3² = 9  

**Passo 4: Variância (média dos quadrados)**  
[9 + 1 + 1 + 9] = 5


**Passo 5: Desvio Padrão**  
Raiz Quadrada de 5 = 2,24


---

## ✅ Conclusão

O desvio padrão mostra que, em média, os valores do conjunto variam cerca de **2,24 unidades** em relação à média (**7**).  

- Valores próximos de **0** → pouca variação  
- Valores maiores → maior dispersão  

---


