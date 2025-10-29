# 📉 Regressão 

Regression analysis is a statistical method used to examine the relationship between two or more variables. It is a powerful tool for predicting future outcomes based on past data. 

There are two main types of regression analysis:  
- **Simple Linear Regression**  
- **Multiple Linear Regression** 

## 🔹 Simple Linear Regression

Statistical technique used to model the relationship between two variables: a dependent variable and an independent variable. 

The dependent variable is the variable we want to predict, while the independent variable is the variable that we use to make the prediction.

In simple linear regression, we assume that there is a linear relationship between the two variables, which means that the change in the independent variable is directly proportional to the change in the dependent variable.

Let´s say, for example, let’s say we want to predict a person’s weight based on their height. In this case, weight is the dependent variable, and height is the independent variable. We would collect data on the heights and weights of a sample of individuals and use this data to create a regression model. The model would allow us to predict a person’s weight based on their height.

### Equation: 

$$
Y = aX + b
$$

Where:  
- **Y:** dependent variable (predicted value)  
- **a:** slope of the line  
- **X:** input data  
- **b:** intercept (value of Y when X = 0)  

## 🔹 Multiple Linear Regression

**Multiple linear regression** extends simple linear regression by using **two or more independent variables** to predict a single dependent variable.  

It helps to understand how **multiple factors** influence the outcome.  

For example, predicting a house price (Y) based on:  
- Size of the house (X₁)  
- Number of rooms (X₂)  
- Location score (X₃)  

### Equation: 

$$
Y = a_1X_1 + a_2X_2 + ... + a_nX_n + b
$$

Where:  
- **Y:** dependent variable (predicted value)  
- **X₁, X₂, ..., Xₙ:** independent variables  
- **a₁, a₂, ..., aₙ:** coefficients of each independent variable  
- **b:** intercept  

---

### 💡 Summary

| Type | Description | Equation | Variables |
|-------|-------------|-----------|------------|
| **Simple Linear Regression** | Relationship between two variables | \( Y = aX + b \) | 1 independent variable |
| **Multiple Linear Regression** | Relationship between one dependent variable and multiple independent variables | \( Y = a_1X_1 + a_2X_2 + ... + a_nX_n + b \) | 2 or more independent variables |

---

### 🧠 Key Idea

Regression models allow us to **understand relationships** between variables and **make predictions**.  
They are essential tools in **data analysis**, **statistics**, and **machine learning**.
