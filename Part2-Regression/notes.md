# Regression 迴歸分析筆記

## 目錄

- [Regression 迴歸分析筆記](#regression-迴歸分析筆記)
  - [目錄](#目錄)
  - [迴歸分析介紹](#迴歸分析介紹)
  - [迴歸模型類型](#迴歸模型類型)
    - [1. Simple Linear Regression](#1-simple-linear-regression)
    - [2. Multiple Linear Regression](#2-multiple-linear-regression)
    - [3. Polynomial Regression](#3-polynomial-regression)
    - [4. Support Vector Regression](#4-support-vector-regression)
    - [5. Decision Tree Regression](#5-decision-tree-regression)
    - [6. Random Forest Regression](#6-random-forest-regression)
  - [評估模型](#評估模型)
## 迴歸分析介紹

迴歸分析是一種統計分析方法，用於：

1. **預測**: 建立自變數(x)與應變數(y)之間的關係，用於預測未知的 y 值
2. **關係分析**: 了解變數之間的相關性和影響程度
3. **模型解釋**: 提供數學模型來解釋現象

## 迴歸模型類型

### 1. Simple Linear Regression

[詳細筆記](./simple_linear_regression/notes.md)

最基本的迴歸模型，用於建立單一自變數與應變數之間的線性關係。

- 基本方程式：y = β₀ + β₁x + ε
- 使用最小平方法(OLS)估計參數
- 適用於簡單的線性關係預測

### 2. Multiple Linear Regression

[詳細筆記](./multiple_linear_regression/note.md)

處理多個自變數的線性迴歸模型。

- 模型建立方法：All-in, Backward Elimination, Forward Selection, Bidirectional Elimination
- 需要注意多重共線性問題
- 特徵縮放的重要性

### 3. Polynomial Regression

[詳細筆記](./polynomial_regression/note.md)

用於建立非線性關係的迴歸模型。

- 可以捕捉複雜的非線性模式
- 需要注意過擬合問題
- 適用於明顯非線性的數據關係

### 4. Support Vector Regression

[詳細筆記](./support_vector_regression/note.md)

基於支持向量機理論的迴歸模型。

- 使用核函數處理非線性問題
- 對異常值不敏感
- 適合處理高維數據

### 5. Decision Tree Regression

[詳細筆記](./decision_tree_regression/note.md)

基於決策樹的迴歸模型。

- 通過將數據分割成多個子集來進行預測
- 易於理解和解釋
- 可以處理非線性關係和類別特徵
- 不需要特徵縮放

### 6. Random Forest Regression

[詳細筆記](./random_forest_regression/note.md)

基於多個決策樹的集成學習迴歸模型。

- 結合多個決策樹的預測結果
- 具有更好的泛化能力
- 減少過擬合風險
- 可以評估特徵重要性


## 評估模型

### 1. R-squared (R²)

R-squared 是統計學和機器學習中常用的評估指標，用於衡量模型的解釋能力。其值介於 0 和 1 之間，通常用於線性回歸模型來表示擬合效果。

#### 計算公式

$$
R^2 = 1 - \frac{SS_{res}}{SS_{tot}}
$$

其中：
- ${SS_{res}}$ (殘差平方和)：模型預測值和真實值之間的誤差平方和
- ${SS_{tot}}$ (總平方和)：真實值和真實值平均數之間的誤差平方和

#### 數值解釋

- R² = 0：模型預測能力很差
- R² = 1：模型完美擬合
- R² = 0.7：模型解釋了 70% 的變異量

#### 優點與限制

優點：
- 可用於評估模型擬合效果
- 便於比較不同模型的表現
- 直觀易懂

限制：
- 不適用於非線性模型評估
- 不代表因果關係
- 可能受過度擬合影響

#### Adjusted R-squared

為改進版本，考慮模型中變數數量的影響，是更可靠的評估指標。

### 2. 迴歸模型比較

| 模型類型 | 優點 | 缺點 |
|---------|------|------|
| 線性回歸 | - 適用於各種規模數據集<br>- 提供特徵相關性信息 | - 需滿足線性回歸假設 |
| 多項式回歸 | - 適用於各種規模數據集<br>- 適合非線性問題 | - 需選擇適當多項式階數<br>- 需平衡偏差/方差 |
| SVR | - 適應性強<br>- 適合非線性問題<br>- 抗異常值 | - 需特徵縮放<br>- 較難理解 |
| 決策樹回歸 | - 可解釋性強<br>- 無需特徵縮放<br>- 適用於線性/非線性問題 | - 小數據集效果差<br>- 易過擬合 |
| 隨機森林回歸 | - 功能強大準確<br>- 適合多種問題類型 | - 可解釋性低<br>- 易過擬合<br>- 需調整樹數量 |