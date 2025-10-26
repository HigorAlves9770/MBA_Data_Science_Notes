# 🧠 Teste de Hipóteses

**O teste t é um teste estátistico usado para determinar se há diferença significativa entre dois grupos ou entre a média de uma amostra ou um valor conhecido**. 

Útil com amostras pequenas ou quando o desvião padrão é desconhecido

Sumary:
1. [T-test](#t-test)  
2. [Z-test](#z-test)  
3. [Qui-Quadrado test](#qui-quadrado-test)  
4. [ANOVA test](#anova-test)  

---

## ⚙️ Etapas do Teste

### 🧩 1. Formulação das Hipóteses

A primeira etapa é **formular uma pergunta de pesquisa** em duas hipóteses concorrentes:

- **Hipótese Nula (HO):** Essa é a suposição de que **não há efeito ou diferença**.  
- **Hipótese Alternativa (Ho):** Essa é a hipótese de que **há efeito ou diferença**.

---

### 📊 2. Coleta e Preparação dos Dados

Nesta etapa, você **coleta e organiza** os dados que serão analisados no teste.

---

### 🧮 3. Escolher o Teste Apropriado

Escolha o **teste estatístico adequado** com base no tipo de dados e na questão de pesquisa.

---

## 🔍 Tipos de Teste

1. **T-test**  
2. **Z-test**  
3. **Qui-quadrado**  
4. **Anova Test (Análise de Variância)**

---

# <a id="t-test"></a>1️⃣ T-test

O **teste t** é um teste estatístico usado para determinar se há **diferença significativa entre dois grupos** ou entre **a média de uma amostra e um valor conhecido**.

📌 **Quando usar:**  
- Amostras pequenas  
- Quando o desvio padrão da população é desconhecido  

A fórmula é:

$$
T = \frac{\bar{x} - \mu}{s / \sqrt{n}}
$$


Onde:  
- `x̄` = média da amostra  
- `μ` = média da população  
- `s` = desvio padrão da amostra  
- `n` = tamanho da amostra  

---

## 🧪 One Sample T-test (Uma Amostra)

Compara a média de uma **única amostra** com um valor **conhecido**.

📘 **Exemplo:**  
Uma fábrica afirma que as garrafas têm em média **500 ml**. Após a coleta de **20 garrafas**, a média encontrada foi **492 ml**.

💭 **Pergunta:** Será que a média real é 500 ml ou a fábrica está entregando menos?  
**H0:** μ = 500 ml

```python
import numpy as np
from scipy import stats

# Dados coletados (ml das garrafas)
data = np.array([492, 495, 488, 490, 493, 491, 489, 494, 492, 487])

# Hipótese H0: média = 500
t_statistic, p_value = stats.ttest_1samp(data, 500)

print("t =", t_statistic, " | p-value =", p_value)

t = -10.81938599461596  |  p-value = 1.8508787160050282e-06
```

📈 **Interpretação:**

- `t = -10.81` → Quanto mais distante de 0, **maior é a evidência contra Ho**.  
- `p-value = 1.85e-06` → **Rejeitamos H0**, ou seja, as garrafas estão sendo entregues com **menos volume do que o declarado**.

---

## 👥 Independent T-test (Duas Amostras)

📘 **Exemplo:** Comparar o **método de ensino antigo** com o **novo método**.

| Grupo | Dados | Média |
|--------|--------|--------|
| A | 6.5, 6.7, 7.0, 6.3, 7.2 | 6.74 |
| B | 6.6, 6.8, 6.9, 6.5, 7.0 | 6.76 |

```python
import numpy as np
from scipy import stats
import matplotlib.pyplot as plt

group_A = np.array([6.5, 6.7, 7.0, 6.3, 7.2])
group_B = np.array([6.6, 6.8, 6.9, 6.5, 7.0])

mean_A = np.mean(group_A)
mean_B = np.mean(group_B)

# Teste t de Student para amostras independentes
t_statistic, p_value = stats.ttest_ind(group_A, group_B)

print(f"Média do Grupo A: {mean_A:.2f}")
print(f"Média do Grupo B: {mean_B:.2f}")
print(f"t = {t_statistic:.3f} | p-value = {p_value:.3f}")

if p_value < 0.05:
    print("→ Rejeitamos H₀: existe diferença significativa entre os métodos.")
else:
    print("→ Não rejeitamos H₀: não há diferença significativa entre os métodos.")
```
Média do Grupo A: 6.74 <br>
Média do Grupo B: 6.76 <br>
t = -0.211 | p-value = 0.839 <br>
→ Não rejeitamos H0: não há diferença significativa entre os métodos. <br>

📈 Interpretação: <br>
<br>
O p-valor = 0.839 é muito maior que 0.05, portanto não há diferença estatisticamente significativa entre os grupos.

# <a id="z-test"></a>2️⃣ Z-test

**É usado quando o tamanho da amostra é grande. Em grandes amostras, a distribuição amostra é normal da média, o que justifica o uso do Z-test**

OBS: O teorema do limite central: Garante que para uma amostra grande a distribuição amostral da média seja aproximadamente normal

| Aspect                | T-test              | Z-test                          |
|-----------------------|---------------------|---------------------------------|
| Sample size           | Small               | Large                           |
| Population variance   | Unknown             | Known                           |
| Distribution          | T-Distribution      | Normal distribution             |
| Application           | Small sample studies| Large sample studies            |

# <a id="qui-quadrado-test"></a>3️⃣ Qui-Quadrado test

# <a id="anova-test"></a>4️⃣ ANOVA test

| Aspect                | T-test               | Z-test                         | Qui-quadrado                 | ANOVA                            |
|---------------------------|------------------------|-----------------------------------|----------------------------------|-------------------------------------|
| Sample size            | Small                  | Large                             | Large                            | Varies (2 or more groups)          |
| Population variance    | Unknown                | Known                             | Not applicable                   | Unknown                            |
| Distribution           | T-Distribution         | Normal distribution               | Chi-square distribution          | F-Distribution                     |
| Application            | Small sample studies   | Large sample studies (Known variance) | Categorical data analysis     | Compare means of multiple groups   |

---

### 🧮 One-Way ANOVA

**ANOVA** stands for **Analysis of Variance**, a statistical test used to compare the means of three or more groups. It analyzes the variance **within the group** and **between groups**. The primary objective is to assess whether the observed variance between group means is more significant than within the groups.

📊 **Formula:**

$$
F = \frac{\text{Mean Square Between Groups}}{\text{Mean Square Within Groups}}
$$

### 🔹 Types of Variation:
- 🔸 **Between-group variation** (due to the factor)  
- 🔹 **Within-group variation** (due to random error)

If the **F-statistic** is sufficiently large, it indicates that **at least one of the group means** is significantly different from the others.

---

### 🧮 Two-Way ANOVA

**ANOVA** stands for **Analysis of Variance**, a statistical test used to compare the means of groups based on **two independent variables**. It analyzes the variance **within the group** and **between groups**, considering the effects of each factor and their possible **interaction effect**. The primary objective is to assess whether the observed variance between group means is more significant than within the groups.

📊 **Formula:**

$$
F = \frac{\text{Mean Square Between Groups}}{\text{Mean Square Within Groups}}
$$


### 🔹 Types of Variation:
- **Main effect of Factor A** (due to the first independent variable)  
- **Main effect of Factor B** (due to the second independent variable)  
- **Interaction effect (A × B)** (how the two factors combined affect the outcome)  
- **Within-group variation** (due to random error)

If the **F-statistic** is sufficiently large for any of the effects, it indicates that there is a **significant difference** related to that factor or interaction.

---

## 🧪 Practical Example with one way ANOVA

Imagine you’re evaluating the effect of three types of diet on weight loss among a group of people:

🥩 **Diet A:** High-protein  
🍞 **Diet B:** High-carbohydrate  
🥗 **Diet C:** Mediterranean  

We want to know whether the type of diet actually affects the average weight loss after a certain period.

### Hypotheses

- **H₀ (Null hypothesis):** The mean weight loss is equal across the three diet groups.  
- **H₁ (Alternative hypothesis):** At least one group’s mean differs significantly.

The **one-way ANOVA** is the right choice here because we have **one independent variable** (type of diet) with **three groups** and **one dependent variable** (weight loss).

If the result is statistically significant (**p < 0.05**), we can conclude that **at least one diet is more effective than the others**.

---

## 🔬 Practical Example with Two-Way ANOVA

Now, suppose that besides the type of diet, you also want to consider the **level of physical activity**:

🛋️ **Sedentary**  
🚶 **Moderate**  
🏋️ **Intense**  

So now we have **two independent variables**:

1️ -> **Type of diet**  
2️ -> **Level of physical activity**  

And **one dependent variable:** weight loss.

In this case, we use **two-way ANOVA**, which tests three main things:

1. **Main effect of factor 1 (Diet):** Does the diet type influence weight loss?  
2. **Main effect of factor 2 (Exercise):** Does the level of exercise affect weight loss?  
3. **Interaction effect:** Does the effectiveness of the diet depend on the level of physical activity?

For example, the test might show that:

- 💪 People on a **high-protein diet** lose more weight when they perform **intense workouts**.  
- 🥗 For the **Mediterranean diet**, the difference between exercise levels is **smaller**.

These interactions help us better understand how **multiple factors work together** to influence the outcome.

## Exemplo Prático em python: One Way

### 🎯 Problema

Um professor quer descobrir se **três métodos de ensino diferentes**  
(**vídeo-aula**, **livro** e **tutoria**) afetam o desempenho dos alunos de forma significativa.

### 🧩 Hipóteses

- **H₀:** As médias das notas dos três métodos são iguais.  
- **H₁:** Pelo menos um método tem média diferente.

---

### 💻 Código Python

````python
import pandas as pd
import scipy.stats as stats

# -------------------------------
# 🎯 ANOVA One-Way — Exemplo prático
# -------------------------------

# Notas dos alunos por método de ensino
video_aulas = [8.5, 7.8, 9.0, 8.2, 8.7]
livros = [7.0, 6.8, 7.5, 7.2, 6.9]
tutoria = [9.2, 8.8, 9.5, 9.0, 9.3]

# Criando DataFrame para exibir melhor os dados
df = pd.DataFrame({
    'Video-Aula': video_aulas,
    'Livro': livros,
    'Tutoria': tutoria
})

print("========== DADOS DE ENTRADA ==========")
print(df.describe().round(2))
print("\n")

# -------------------------------
# 🧮 Realizando o teste ANOVA de uma via
# -------------------------------
f_stat, p_value = stats.f_oneway(video_aulas, livros, tutoria)

print("========== RESULTADO ANOVA ONE-WAY ==========")
print(f"Estatística F: {f_stat:.4f}")
print(f"Valor-p: {p_value:.6f}\n")

# -------------------------------
# 📊 Interpretação detalhada
# -------------------------------
alpha = 0.05

print("========== INTERPRETAÇÃO ==========")
if p_value < alpha:
    print("✅ Rejeitamos a hipótese nula (H₀).")
    print("➡️ Conclusão: Pelo menos um dos métodos de ensino possui média de notas diferente dos outros.")
    print("🔍 Isso indica que o método de ensino tem impacto significativo no desempenho dos alunos.")
else:
    print("❌ Não rejeitamos a hipótese nula (H₀).")
    print("➡️ Conclusão: Não há evidências suficientes para afirmar que as médias são diferentes.")
    print("🔍 Ou seja, o método de ensino não parece influenciar significativamente as notas.")

# -------------------------------
# 📋 Resumo final interpretativo
# -------------------------------
print("\n========== RESUMO FINAL ==========")
print(f"🧠 Estatística F calculada: {f_stat:.4f}")
print(f"🎯 Valor-p obtido: {p_value:.6f}")
print(f"📏 Nível de significância (alpha): {alpha}")
print(f"📘 Decisão: {'Rejeitar H₀' if p_value < alpha else 'Não rejeitar H₀'}")
print(f"📈 Interpretação: {'Existe diferença significativa entre os grupos.' if p_value < alpha else 'As médias são estatisticamente iguais.'}")

========== RESULTADO ANOVA ONE-WAY ==========
Estatística F: 24.5214
Valor-p: 0.000103

✅ Rejeitamos a hipótese nula (H₀).
➡️ Conclusão: Pelo menos um dos métodos de ensino possui média de notas diferente dos outros.
🔍 O método de ensino tem impacto significativo no desempenho dos alunos.


````

##  Exemplo Prático em python: Two Way

### 🎯 Problema

O professor também quer saber se o **turno de estudo** (manhã ou tarde) influencia nas notas, além do método de ensino.  
Ou seja, ele quer avaliar **dois fatores**:

1. Método de ensino  
2. Turno (manhã/noite)  

E verificar se há **interação entre eles**.

---

### 🧩 Hipóteses

- **H₀₁:** As médias são iguais entre os métodos.  
- **H₀₂:** As médias são iguais entre os turnos.  
- **H₀₃:** Não há interação entre método e turno.

---

### 💻 Código Python

````python
import pandas as pd
import statsmodels.api as sm
from statsmodels.formula.api import ols

# -------------------------------
# 🎯 Exemplo: Efeito do método de ensino e do turno nas notas dos alunos
# -------------------------------
data = {
    'Metodo': ['Video', 'Video', 'Video', 'Livro', 'Livro', 'Livro', 'Tutoria', 'Tutoria', 'Tutoria'] * 2,
    'Turno': ['Manha'] * 9 + ['Tarde'] * 9,
    'Nota': [8.5, 8.2, 8.7, 7.0, 7.3, 7.1, 9.0, 8.9, 9.2,
             8.8, 8.5, 8.9, 6.8, 7.1, 7.0, 9.1, 9.0, 9.3]
}

df = pd.DataFrame(data)

# -------------------------------
# 🧮 ANOVA Two-Way
# -------------------------------
modelo = ols('Nota ~ C(Metodo) + C(Turno) + C(Metodo):C(Turno)', data=df).fit()
anova_resultado = sm.stats.anova_lm(modelo, typ=2)

print("========== RESULTADO ANOVA TWO-WAY ==========")
print(anova_resultado, "\n")

# -------------------------------
# 📊 Interpretação
# -------------------------------
print("========== INTERPRETAÇÃO ==========")
alpha = 0.05
for fator in anova_resultado.index:
    p = anova_resultado.loc[fator, 'PR(>F)']
    if p < alpha:
        print(f"✅ {fator}: efeito significativo (p = {p:.4f})")
    else:
        print(f"❌ {fator}: sem efeito significativo (p = {p:.4f})")

print("\nConclusão:")
print("➡️ O teste avalia se o método de ensino, o turno, ou a combinação dos dois influenciam as notas.")

========== RESULTADO ANOVA TWO-WAY ==========
                          sum_sq    df         F    PR(>F)
C(Metodo)              14.823333   2.0  90.06122  0.000000
C(Turno)                0.100000   1.0   1.21519  0.285641
C(Metodo):C(Turno)      0.033333   2.0   0.20253  0.818394
Residual                1.317778  12.0       NaN       NaN

========== INTERPRETAÇÃO ==========
✅ C(Metodo): efeito significativo (p = 0.0000)
❌ C(Turno): sem efeito significativo (p = 0.2856)
❌ C(Metodo):C(Turno): sem efeito significativo (p = 0.8184)

➡️ O método de ensino afeta significativamente as notas dos alunos, 
mas o turno (manhã ou tarde) e a interação entre eles não tiveram impacto relevante.

````
