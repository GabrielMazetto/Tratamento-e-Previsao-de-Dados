# 🚀 Análise do Dataset Abalone: Da Imputação à Previsão Sustentável

Este projeto desenvolve uma solução completa de Machine Learning para o dataset Abalone, com o objetivo principal de automatizar a determinação da idade desses moluscos (contagem de anéis) de uma forma mais eficiente, econômica e sustentável.

O trabalho foi dividido em três fases estratégicas: tratamento de dados, redução de dimensionalidade e construção de um modelo preditivo.

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)

## ✨ Principais Fases e Descobertas

### 1. Imputação de Dados com Machine Learning
O primeiro passo foi resolver o problema de dados faltantes na base. Para isso, foi utilizada a técnica de **imputação por K-Nearest Neighbors (KNN)**, uma abordagem que estima os valores ausentes com base nos abalones mais similares, garantindo um preenchimento mais preciso e realista do que métodos estatísticos simples.

### 2. Redução de Dimensionalidade Estratégica
Na busca por otimizar a coleta de dados, foi realizada uma análise de correlação para reduzir o número de atributos necessários. Os atributos foram divididos em grupos (Dimensões e Pesos) e, com base em suas redundâncias, o conjunto de dados foi simplificado para apenas três características principais: **`Diameter`**, **`Height`** e **`Whole weight`**.
* Foram descartados o `Length` (por sua alta correlação com `Diameter`) e os pesos individuais (`Shucked`, `Viscera`, `Shell`), que já estão contidos no `Whole weight`.

### 3. Uma Abordagem Sustentável e Não-Destrutiva
A maior revelação desta etapa foi que os três atributos restantes (`Diameter`, `Height`, `Whole weight`) **não exigem a morte do animal para serem medidos**. Isso transformou fundamentalmente a abordagem do projeto, tornando-a não apenas mais eficiente, mas também **sustentável e ética**, um benefício imensurável em relação ao método tradicional que envolve a dissecação do abalone.

### 4. Previsão, Avaliação e o Trade-off Positivo
Utilizando o conjunto de dados reduzido, foram testados e avaliados múltiplos modelos de regressão, incluindo **K-Nearest Neighbors (KNN)** e **Regressão Linear Multivariada**.

A análise comparativa (avaliada por R², MAE, MSE e RMSE) mostrou que a diferença de performance entre os modelos não era grande. Diante disso, a **Regressão Linear** foi escolhida como modelo final devido à sua **melhor explicabilidade** e interpretabilidade.

Essa escolha permitiu extrair a fórmula de previsão, que é composta por:
`y (Rings) = 0.40*Diameter - 0.07*Whole weight + 0.28*Height + 0.0002`

A análise também confirmou que a redução de dimensionalidade causou uma leve e aceitável diminuição na precisão geral, um trade-off massivamente compensado pelos ganhos em eficiência e sustentabilidade.

## 💡 Conclusão

O projeto foi além de uma simples previsão. Ele redesenhou o processo de análise, provando ser possível substituir um método caro, demorado e destrutivo por uma solução de Machine Learning rápida, econômica e sustentável, que entrega resultados com precisão satisfatória para fins práticos.

## 🛠️ Tecnologias Utilizadas

* **Python**
* **Pandas** e **NumPy:** Para manipulação e análise dos dados.
* **Matplotlib** e **Seaborn:** Para visualização e análise de correlação.
* **Scikit-learn:**
    * `KNNImputer`: Para a imputação de dados faltantes.
    * `StandardScaler`: Para normalização dos dados.
    * `LinearRegression`: Para a construção do modelo preditivo.
    * `train_test_split`, `r2_score`, `mean_absolute_error`, `mean_squared_error`: Para divisão e avaliação do modelo.
