# 章節導讀（繁體中文快速指南）

給自己看的學習筆記索引，涵蓋 Jake VanderPlas *Python Data Science Handbook* 的五大部分。專業名詞維持英文，方便對照書本原文。

這本書是純「工具書」，教你怎麼熟練使用 Python 資料科學工具鏈；跟 [`machine-learning-book`](../machine-learning-book/STUDY_GUIDE_zh-TW.md)（*Machine Learning with PyTorch and Scikit-Learn*）互補——那本教機器學習「方法」，這本教操作「工具」。第 5 部分 Machine Learning 跟那本書的古典 ML 章節(ch01–ch10)有重疊，重疊處已在下方標註對應章節。

---

## Part 1 — IPython：不是 ML 內容，是開發環境技巧
單純是 IPython/Jupyter 的操作技巧（`?`/`??` 查文件、tab 補全、`%magic` 指令、`%timeit` 效能量測、debugger）。跟機器學習概念無關，用到的時候查就好，不用特別排時間讀。
**檔案**：`01.00`–`01.08`

## Part 2 — NumPy：陣列運算基礎（幾乎所有後續章節的地基）
**在做什麼**：理解 NumPy 的核心——用固定型別的陣列取代 Python list，換取向量化運算的速度。
**關鍵概念**：ndarray、data types、vectorization / universal functions (ufuncs)、aggregation（min/max/sum等）、broadcasting（不同形狀陣列如何相加）、boolean masking、fancy indexing、sorting、structured arrays
**檔案**：`02.00`–`02.09`
**為什麼重要**：`machine-learning-book` 的 ch02、ch11（手刻 perceptron / 神經網路）幾乎全部用 NumPy 陣列運算寫成，這部分不熟，那兩章會讀得很痛苦。

## Part 3 — Pandas：表格資料處理
**在做什麼**：學會用 `DataFrame`／`Series` 處理有欄位名稱、有缺值、需要合併/分組的真實表格資料。
**關鍵概念**：`Series` / `DataFrame`、indexing/selection（`.loc`/`.iloc`）、missing data（`NaN` 處理）、hierarchical indexing（多層索引）、concat/merge/join（合併資料集）、groupby（aggregation）、pivot table、字串向量化操作、時間序列、`eval()`/`query()` 效能優化
**檔案**：`03.00`–`03.13`
**為什麼重要**：直接對應 `machine-learning-book` ch04（資料前處理）、ch08（文字資料）、ch09（Ames Housing 資料集）裡讀資料、清理資料的操作，那些章節預設你已經會這裡教的東西。

## Part 4 — Matplotlib（+ Seaborn）：資料視覺化
**在做什麼**：從基本折線圖/散佈圖，到誤差棒、密度圖、直方圖、圖例/色條客製化、多子圖排版，最後介紹 Seaborn 這個更高階、統計繪圖導向的套件。
**關鍵概念**：`plt.plot`/`plt.scatter`、errorbar、density & contour plot、histogram/binning、legend/colorbar 客製化、subplots、annotation、tick 客製化、3D plotting、Seaborn 統計繪圖
**檔案**：`04.00`–`04.15`
**為什麼重要**：`machine-learning-book` 每一章幾乎都用 Matplotlib 畫結果圖（decision boundary、loss curve、confusion matrix 等），這部分是讀懂那些圖表程式碼的前提。

## Part 5 — Machine Learning：跟 `machine-learning-book` 重疊的部分
這是唯一跟另一本書內容重疊的部分，用 scikit-learn 快速掃過整個古典 ML 全景，深度不如 `machine-learning-book`，但涵蓋範圍略有不同（互補多於重複）。

| PDSH 小節 | 在做什麼 | 對應 `machine-learning-book` |
|---|---|---|
| What Is ML / Introducing Scikit-Learn | ML 基本概念、scikit-learn Estimator API 介紹 | ch01, ch03 |
| Hyperparameters and Model Validation | train/validation split、cross-validation、bias-variance | ch06 |
| Feature Engineering | 類別特徵、文字特徵、影像特徵、缺值補值 | ch04 |
| **Naive Bayes**（本書獨有） | 貝氏定理、Gaussian/Multinomial Naive Bayes、文件分類 | *無對應章節* |
| Linear Regression | 簡單/多項式迴歸、basis function regression、regularization | ch09 |
| Support Vector Machines | maximum margin、kernel trick、soft margin | ch03 |
| Random Forests | decision tree、bagging、random forest | ch03、ch07 |
| Principal Component Analysis | PCA 降維、noise filtering、eigenfaces | ch05 |
| **Manifold Learning**（本書獨有，較完整） | multidimensional scaling、Isomap、LLE 等非線性降維 | ch05 只淺提 t-SNE，這裡更完整 |
| K-Means | k-means clustering、應用案例(手寫數字、色彩壓縮) | ch10 |
| **Gaussian Mixture Models**（本書獨有） | 用機率模型做 soft clustering、GMM 用於密度估計/生成 | *無對應章節* |
| **Kernel Density Estimation**（本書獨有） | 非參數密度估計，KDE vs. histogram | *無對應章節* |
| Application: Face Detection Pipeline | 綜合應用：用 HOG 特徵 + SVM 做人臉偵測 | *無對應章節，精神類似 ch14 CNN 影像分類但方法更傳統* |

**檔案**：`05.00`–`05.15`

---

## 用法建議
- Part 1–4 是工具，讀的時候不用求快，邊做 `machine-learning-book` 的章節邊回來查最有效率——例如卡在 `pandas.groupby` 不熟，就回來看 Part 3 對應小節
- Part 5 建議跟 `machine-learning-book` 對照著讀：重疊的主題（迴歸、SVM、隨機森林、PCA、k-means）可以先讀 PDSH 版本建立直覺（篇幅短、範例直觀），再進 `machine-learning-book` 補深度（有完整數學推導與 scikit-learn 進階用法）
- Naive Bayes、Manifold Learning、GMM、KDE 這幾個 PDSH 獨有主題，如果課程大綱要求要教，記得這裡才有教材
