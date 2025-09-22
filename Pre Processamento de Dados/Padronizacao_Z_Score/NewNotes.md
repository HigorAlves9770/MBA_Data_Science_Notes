# 📘 Estudos sobre Z-Score ou standardization (Gaussiana)

## 📌 1. Antes de falae sobre Z-score, temos que entender sobre Distribuição normal/Gaussiana

A **distribuição normal**, também chamada de **distribuição gaussiana**, é uma das distribuições de probabilidade mais importantes em estatística e machine learning.  
Ela descreve dados que se concentram em torno de uma **média**, formando o clássico **"sino"** quando representada graficamente.

(μ) - valor médio <br>
(σ) - O desvio padrão

---

## 📊 2. Características Principais

- **Simétrica** em torno da média (μ).  
- **Média (μ)**, **mediana** e **moda** são iguais.  
- A maioria dos valores está próxima da média; valores extremos são raros.  
- Os **desvios-padrão (σ)** determinam a dispersão:
  - Aproximadamente 68% dos dados estão dentro de 1σ da média.  
  - Aproximadamente 95% estão dentro de 2σ.  
  - Aproximadamente 99,7% estão dentro de 3σ.  
  _(Regra Empírica ou 68-95-99,7)_

---

## 🧮 3. Função de Densidade de Probabilidade (PDF)

A fórmula da PDF da distribuição normal é:

\[
f(x) = \frac{1}{\sigma \sqrt{2\pi}} e^{ -\frac{(x - \mu)^2}{2\sigma^2} }
\]

- **x** → valor da variável aleatória  
- **μ** → média da distribuição  
- **σ** → desvio padrão  
- **e** → base do logaritmo natural (~2,718)

---

## 🎯 4. Intuição

- Valores **próximos à média** têm maior probabilidade.  
- Valores **longe da média** são raros.  
- A forma da curva é **sino**, refletindo a frequência dos valores.  

Exemplo: altura de pessoas, peso, notas de provas normalmente seguem uma distribuição aproximada gaussiana.

---

print("Média:", media)
print("Desvio padrão (população):", desvio)
print("Desvio padrão (amostra):", desvio_amostra)

