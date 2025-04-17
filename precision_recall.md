# Precision & Recall Cheatsheet

---

## 1. Definitions
- **Precision:**  
  ![Precision = TP/(TP+FP)](https://latex.codecogs.com/gif.latex?%5Cmathrm%7BPrecision%7D%3D%5Cfrac%7BTP%7D%7BTP%2BFP%7D)
- **Recall:**  
  ![Recall = TP/(TP+FN)](https://latex.codecogs.com/gif.latex?%5Cmathrm%7BRecall%7D%3D%5Cfrac%7BTP%7D%7BTP%2BFN%7D)
- **F1 Score:**  
  ![F1 = 2PR/(P+R)](https://latex.codecogs.com/gif.latex?F1%3D2%5Cfrac%7BP%5Ccdot%20R%7D%7BP%2BR%7D)

---

## 2. ROC & AUC
- **True Positive Rate (TPR):** same as recall.  
- **False Positive Rate (FPR):**  
  ![FPR = FP/(FP+TN)](https://latex.codecogs.com/gif.latex?%5Cfrac%7BFP%7D%7BFP%2BTN%7D)  
- **AUC:** area under ROC curve.

---

## 3. Precision-Recall Curve
- Plot precision vs recall at different thresholds.  
- **Average Precision (AP):** area under PR curve.  
- **mAP:** mean AP over classes.

---

## 4. Example Confusion Matrix

    Pred Pos   Pred Neg  
    Actual Pos     TP         FN  
    Actual Neg     FP         TN  
