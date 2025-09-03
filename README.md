# 🍽️ NutriNet: Multimodal Meal Nutrition Analysis  

> A multimodal deep learning framework for estimating meal caloric content using **Continuous Glucose Monitoring (CGM)**, **demographic & microbiome data**, and **meal images**.  
> Developed as part of **CSCE 633: Machine Learning** at Texas A&M University (Spring 2025).  

---

## 📌 Overview  

Traditional calorie tracking is **manual, error-prone, and time-consuming**. With the rise of **wearable sensors** and **data-driven health monitoring**, we explore an **automated multimodal solution** that integrates physiological, demographic, and visual data for precise caloric estimation.  

✅ **Key Contributions**  
- Built a **robust preprocessing pipeline** for heterogeneous data modalities (time-series, categorical, numerical, images).  
- Designed a **PyTorch-based multimodal neural network** with late fusion of modality-specific encoders.  
- Achieved **Root Mean Square Relative Error (RMSRE) = 0.3035**, surpassing the baseline benchmark.  

---

## ⚙️ Features  

- **CGM Data Processing**  
  - Extracted glycemic response windows, statistical features, AUC.  
  - Normalized & padded sequences for model compatibility.  

- **Demographic & Microbiome Data**  
  - Categorical: imputation + one-hot encoding.  
  - Numerical: scaling + imputation.  
  - Microbiome vectors: PCA-based dimensionality reduction.  

- **Image Preprocessing**  
  - Resized (64×64), normalized, and converted to PyTorch tensors.  

- **Multimodal Fusion Model**  
  - 🧩 **CGM Encoder**: 1D CNN for glucose time-series.  
  - 🧬 **Demographic Encoder**: Fully connected layers with batch normalization.  
  - 🔗 **Feature Fusion**: Late fusion with concatenation → regression layers.  

- **Training**  
  - Custom **RMSRE loss function**.  
  - **Adam optimizer**, learning rate scheduling, early stopping.  

---

## 📊 Results  

| Metric | Value |
|--------|-------|
| Validation RMSRE | **0.3035** |
| Epochs | ~36 (early stopping) |
| Benchmark | Surpassed Kaggle baseline |

✨ Both CGM and demographic data proved essential, highlighting the value of multimodal fusion for nutrition analysis.  

---

## 🚀 Getting Started  

### Prerequisites  
- Python 3.9+  
- [PyTorch >= 2.0](https://pytorch.org/)  
- NumPy, Pandas, scikit-learn  
- Matplotlib / Seaborn  

### Installation  

```bash
git clone https://github.com/<your-username>/NutriNet.git
cd NutriNet
pip install -r requirements.txt
```

### Running the Notebook  

```bash
jupyter notebook NutriNet.ipynb
```

Follow the notebook cells to preprocess the dataset, train the model, and evaluate performance.  

---

## 📈 Future Work  

- Incorporate **meal images** more effectively into the multimodal pipeline.  
- Explore **attention-based fusion mechanisms** for better interpretability.  
- Develop **personalized models** that adapt to individual metabolic responses.  
- Integrate **physical activity data** for richer health context.  

---

## 📜 License  

This project is for **academic use only**. Please contact the authors for permissions before reuse.  

---
