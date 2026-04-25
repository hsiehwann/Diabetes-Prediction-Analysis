# Diabetes-Prediction-Analysis

此專案旨在開發一個機器學習模型，用於預測患者是否患有糖尿病。除了追求高預測準確率，本專案特別著重於模型解釋性，分析各項生理指標（如血糖、BMI 等）如何影響預測結果，以提供更具參考價值的醫療洞察。

核心流程包含：

  1.資料預處理：處理重複值、特徵縮放。

  2.類別平衡：使用演算法驅動技術解決資料集中正負樣本不均的問題。

3.模型建構：評估 Logistic Regression, SVM, 以及 Artificial Neural Networks (ANN)。

4.模型評估：採用 5-Fold Cross-Validation，並以 ROC/AUC 與 F1-score 作為主要衡量指
標。

5.模型解釋：導入 SHAP (SHapley Additive exPlanations) 解釋特徵對模型輸出貢獻。

資料集：
本專案使用 CDC (Centers for Disease Control and Prevention) 提供的 BRFSS 2015 (Behavioral Risk Factor Surveillance System) 資料集。樣本數大於 25 萬筆，涵蓋了行為風險、慢性健康狀況及預防性醫療服務的使用情況。

模型效能：
<img width="777" height="520" alt="AUC" src="https://github.com/user-attachments/assets/0381c37c-f975-4b64-a117-9ce27c441eab" />
<img width="1018" height="217" alt="OVERALL" src="https://github.com/user-attachments/assets/14764cbb-36ea-4820-b5a1-056330564703" />
1.整體模型表現：所有模型的 AUC 均達到 0.82 以上，顯示模型具備良好的辨識能力，說明模型能有效區分糖尿病患者與健康受訪者。且在綜合指標中 RECALL 平均達 0.85 以上，代表模型能正確抓取大部分患有糖尿病風險的患者。

2.ANN 表現最佳：ANN以 AUC = 0.830 略勝一籌，這表明 ANN 能更好地捕捉 BRFSS 資料集中複雜且非線性的特徵交互關係。


可解釋性：
<img width="616" height="739" alt="SHAP" src="https://github.com/user-attachments/assets/56459c8a-9721-463f-a27e-beedaf41dc57" />
1.關鍵因素：GenHlth (自評健康狀況) 是模型預測最依賴的特徵。圖表顯示，當自評健康狀況較差時，會大幅顯著增加被預測為糖尿病的機率。

2.生理指標影響：Age (年齡) 與 BMI 緊隨其後。年齡越大、BMI 越高，患病風險越正向增加。此外，HighBP (高血壓) 與 HighChol (高膽固醇) 也是重要的正向風險因子。
