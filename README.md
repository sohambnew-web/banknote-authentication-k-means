
# 💵 Banknote Authentication using K-Means Clustering

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange?style=for-the-badge&logo=scikit-learn)
![NumPy](https://img.shields.io/badge/NumPy-Array%20Computing-013243?style=for-the-badge&logo=numpy)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557c?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

> **IBM Data Science Foundation — Final Project (Coursera)**
> An unsupervised machine learning project to detect counterfeit banknotes using K-Means Clustering.

---

## 📌 Project Overview

This project applies **K-Means Clustering**, an unsupervised machine learning algorithm, to distinguish **real banknotes from fake ones** — without any manual labeling. Features are extracted from banknote images using **Wavelet Transforms**, and the algorithm finds natural groupings in the data.

The core idea: real and fake banknotes differ in their microscopic texture patterns. These differences show up clearly when we analyze the image data mathematically.

---

## 🧠 What is K-Means Clustering?

K-Means is an **unsupervised learning** algorithm that:
1. Randomly places K cluster centers in the data space
2. Assigns each data point to the nearest center
3. Recalculates centers as the mean of all assigned points
4. Repeats until the centers stop moving (convergence)

It finds hidden groups in data **without needing labeled examples** — perfect for fraud detection scenarios where labeling every banknote manually is impractical.

---

## 📊 Dataset

**Source:** [UCI Banknote Authentication Dataset](https://archive.ics.uci.edu/ml/datasets/banknote+authentication)

The dataset contains **1,372 banknote samples**, each described by 4 features extracted from grayscale images using **Wavelet Transform**:

| Feature | Description |
|--------|-------------|
| `V1` | Variance of wavelet-transformed image |
| `V2` | Skewness of wavelet-transformed image |
| `V3` | Kurtosis of wavelet-transformed image |
| `V4` | Entropy of image |

> Only `V1` and `V2` were used in this project to keep the analysis 2-dimensional and visually interpretable.

---

## 🛠️ Libraries Used

| Library | Purpose |
|--------|---------|
| `NumPy` | Numerical computations (mean, std, array operations) |
| `Pandas` | Loading and handling the CSV dataset |
| `Matplotlib` | Plotting scatter plots and cluster visualizations |
| `Scikit-Learn` | K-Means clustering algorithm |

---

## 🚀 How to Run

### 1. Clone the repository
```bash
git clone https://github.com/your-username/banknote-kmeans.git
cd banknote-kmeans
```

### 2. Install dependencies
```bash
pip install numpy pandas matplotlib scikit-learn
```

### 3. Run the Jupyter Notebook
```bash
jupyter notebook Jupyter_Banknote_Project_1.ipynb
```

---

## 🔍 Project Workflow

```
Load Dataset (CSV)
       ↓
Extract Features V1 and V2
       ↓
Compute Basic Statistics (Mean, Std Dev)
       ↓
Combine into 2D Array
       ↓
Apply K-Means (k = 2, 3, 4, 5)
       ↓
Plot Clusters and Visualize Centroids
       ↓
Identify Best k for Real vs Fake separation
```

---

## 📈 Results

The algorithm was tested with **k = 2, 3, 4, and 5** clusters:

| k value | Observation |
|--------|-------------|
| `k = 2` | ✅ Best result — clearly separates real vs. fake banknotes |
| `k = 3` | Splits one natural group unnecessarily |
| `k = 4` | Further over-segmentation |
| `k = 5` | Too many clusters for a binary problem |

**Key Finding:** The banknote data naturally forms **2 distinct clusters** in the V1-V2 feature space, corresponding to genuine and counterfeit notes. K-Means with `k=2` successfully identifies this separation without any labeled training data.

---

## 💡 Key Concepts Learned

- **Unsupervised Machine Learning** — finding patterns without labels
- **Wavelet Transform** — extracting texture features from images
- **K-Means Clustering** — iterative centroid-based grouping
- **Exploratory Data Analysis (EDA)** — mean, standard deviation
- **Hyperparameter Tuning** — choosing the right value of k
- **Data Visualization** — scatter plots, cluster center plotting

---

## 🗂️ Project Structure

```
banknote-kmeans/
│
├── Jupyter_Banknote_Project_1.ipynb   # Main notebook
├── Banknote-dataset.csv               # Dataset
└── README.md                          # This file
```

---

## 🎓 Course Information

| Detail | Info |
|--------|------|
| **Platform** | Coursera |
| **Course** | IBM Data Science Foundations |
| **Project Type** | Final Capstone Project |
| **Level** | Beginner |

---

## 👤 Author

**Soham Bhagwat**
- GitHub: [@Soham-data](https://github.com/your-username)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

> *"Data science is not just about algorithms — it's about finding meaning hidden in numbers."*
> 
