# ID3 Decision Tree Classifier (From Scratch)

This project is a Python implementation of the ID3 algorithm to build a decision tree classifier without using any machine learning libraries like scikit-learn. The goal is to classify whether a person's income is `<=50K` or `>50K` using census data. Everything — from entropy calculation to recursive tree building and pruning — was implemented manually.

---

## 📂 Dataset

The data comes from the UCI Machine Learning Repository: [Adult Data Set](https://archive.ics.uci.edu/ml/datasets/adult). It was preprocessed to include only categorical variables.

**Files used:**
- `census_training.csv` — 30,110 rows for training.
- `census_training_test.csv` — 15,028 rows for testing accuracy.
- `playtennis.csv` & `emails.csv` — small datasets used to test tree-building correctness.

---

## ⚙️ Features

- ID3 Algorithm (Information Gain / Entropy)
- Supports categorical features only
- Tree pruning based on minimum partition size
- Manual accuracy calculation on test data
- Dictionary-based tree structure
- Optional Graphviz rendering for tree visualization

---

## 📈 Results

| Dataset         | Accuracy |
|----------------|----------|
| Without Pruning | 80.58%   |
| With Pruning (min partition size = 30) | 81.74%   |

---

## 🖼️ Tree Examples

Here are small example trees generated from `playtennis.csv` and `emails.csv`. These were used to validate the tree-building logic:

<details>
  <summary>Click to view sample tree structure (PlayTennis)</summary>

```python
{
  'outlook': {
    'sunny': {
      'humidity': {
        'high': 'No',
        'normal': 'Yes'
      }
    },
    'overcast': 'Yes',
    'rainy': {
      'wind': {
        'strong': 'No',
        'weak': 'Yes'
      }
    }
  }
}