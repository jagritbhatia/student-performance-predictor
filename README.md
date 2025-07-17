#  Student Performance Predictor

This project applies **decision trees** to predict whether a student will **pass or fail** using real-world academic and behavioral data. It's based on the **UCI Student Performance Dataset** and implemented in **Python (Jupyter Notebook)**.

---

##  Overview

We use a dataset of Portuguese secondary school students with **30 attributes** including:
- Grades (G1, G2, G3)
- Demographics (age, gender, address)
- Family and social info (parents' jobs, romantic relationships, etc.)
- Study-related factors (study time, failures, absences)

We preprocess this data and train a **Decision Tree Classifier** to predict if the student **passes (1)** or **fails (0)**.

---

##  What This Project Covers

-  Data Cleaning & Feature Engineering
-  One-Hot Encoding of categorical variables
-  Creating a binary `pass/fail` target from grades
-  Splitting data into train/test sets
-  Building and evaluating Decision Tree models
-  Cross-validation for accuracy estimation
-  Visualizing accuracy vs tree depth

---

## 🗂️ Project Structure

student-performance-predictor/
├── data/
│ └── student-por.csv # original dataset
├── images/
│ └── accuracy_plot.png # optional accuracy graph
├── student_performance.ipynb # Jupyter notebook (main analysis)
└── README.md # This file


---

##  Dataset Source

UCI Machine Learning Repository:  
🔗 [https://archive.ics.uci.edu/ml/datasets/student+performance](https://archive.ics.uci.edu/ml/datasets/student+performance)

---

##  How It Works 

1. **Load the data** with `pandas` and count rows (`len()` shows 649 students)
2. **Create a target** column `pass`:
   - If (G1 + G2 + G3) ≥ 35 → Pass (1)
   - Else → Fail (0)
3. Drop G1, G2, G3 to prevent data leakage
4. Use `get_dummies()` to one-hot encode all categorical columns
5. **Split** dataset into:
   - Training set (first 500)
   - Testing set (last 149)
6. Build a **Decision Tree** (`max_depth=5`) using `entropy` as the criterion
7. **Evaluate performance** using:
   - `.score()` on test set
   - `cross_val_score()` on entire dataset with 5-fold CV
8. Vary depth from 1 to 20 → find optimal tree size for accuracy

---

##  Sample Output

```bash
Passing: 328 out of 649 (50.54%)
Accuracy: 0.85 (+/- 0.04)


| Tool             | Purpose                           |
| ---------------- | --------------------------------- |
| Python           | Main programming language         |
| pandas           | Data manipulation                 |
| scikit-learn     | Machine learning & decision trees |
| matplotlib       | Plotting accuracy graph           |
| Jupyter Notebook | Analysis environment              |

pip install pandas matplotlib scikit-learn
