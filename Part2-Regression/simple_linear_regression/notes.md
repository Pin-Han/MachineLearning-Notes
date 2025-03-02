# Simple Linear Regression

## 目錄

- [Simple Linear Regression](#simple-linear-regression)
  - [目錄](#目錄)
    - [基本概念](#基本概念)
    - [最小平方法 (OLS)](#最小平方法-ols)
      - [詳細說明](#詳細說明)
    - [實作範例](#實作範例)
      - [簡單數據示例](#簡單數據示例)
    - [使用場景](#使用場景)

### 基本概念

- 定義：y = β₀ + β₁x + ε
- 其中：
  - y 為目標變數（應變數）
  - x 為特徵變數（自變數）
  - β₀ 為截距
  - β₁ 為斜率
  - ε 為誤差項

### 最小平方法 (OLS)

- 定義：尋找最佳的 β₀ 和 β₁ 使得預測誤差平方和最小
- 數學表示：min Σ(y - ŷ)²
- 特點：
  - 計算簡單直觀
  - 結果容易解釋
  - 在特定假設下是最佳線性無偏估計（BLUE）
- 使用條件：
  - 線性關係
  - 誤差項獨立
  - 誤差項方差同質
  - 誤差項常態分配

#### 詳細說明

普通最小平方法（Ordinary Least Squares, OLS）是一種統計技術，用於線性回歸分析中估計模型參數。其目的是通過最小化觀測數據點與回歸線之間的誤差平方和，找到最佳的回歸係數。

1. **目標**：找到一條直線，使得所有數據點到這條直線的垂直距離的平方和最小。

2. **數學形式**

   - 模型假設：y = β₀ + β₁x + ε
     - y：因變量（要預測的值）
     - x：自變量（特徵）
     - β₀：截距
     - β₁：斜率
     - ε：誤差項

3. **損失函數**：使用誤差平方和（Sum of Squared Errors, SSE）
   SSE = Σ(yᵢ - ŷᵢ)² = Σ(yᵢ - (β₀ + β₁xᵢ))²

4. **求解方法**：通過最小化 SSE，計算得到最佳的回歸係數
   - β₁ = Σ((xᵢ - x̄)(yᵢ - ȳ)) / Σ(xᵢ - x̄)²
   - β₀ = ȳ - β₁x̄

### 實作範例

#### 簡單數據示例

假設我們有以下數據點，表示工作經驗（年數）和對應的薪水（千元）：

- x = [1, 2, 3, 4, 5] 表示經驗年數
- y = [3, 4, 2, 5, 6] 表示薪水

**計算步驟：**

1. 計算平均值

   - x̄ = (1 + 2 + 3 + 4 + 5) / 5 = 3
   - ȳ = (3 + 4 + 2 + 5 + 6) / 5 = 4

2. 計算斜率（β₁）
   β₁ = 0.7（詳細計算過程略）

3. 計算截距（β₀）
   β₀ = 4 - 0.7 × 3 = 1.9

4. 最終回歸方程：
   y = 1.9 + 0.7x

### 使用場景

- 適用情況：

  - 當變量之間存在線性關係
  - 數據滿足 OLS 的基本假設
  - 需要簡單直觀的模型解釋

- 實際應用案例：

  - 經濟學：預測收入與支出關係
  - 工程學：材料性能分析
  - 生物學：生長曲線擬合
  - 社會科學：人口趨勢分析

- 限制與注意事項：
  - 僅適用於線性關係
  - 對異常值敏感
  - 需要確保數據滿足基本假設
  - 不適用於複雜的非線性關係
