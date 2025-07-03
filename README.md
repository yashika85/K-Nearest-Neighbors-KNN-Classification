# K-Nearest-Neighbors-KNN-Classification
# Playing with K‑NN on the tiny digits set 🖋️

I wanted something super‑simple to refresh my memory on k‑Nearest‑Neighbours, so I grabbed the built‑in **digits** dataset that ships with Scikit‑learn (those 8×8 pixel images of handwritten numbers) and messed around with it. This repo is basically my scratchpad.

---

## What’s inside

| File / stuff | What it is |
|--------------|------------|
| **MNIST_Digits.xlsx** | Whole dataset in Excel form (64 pixel columns + a `label`) so I can peek at it in both Pandas *and* Excel. |
| **knn_digits.ipynb**  | My Jupyter notebook – load data, scale, split, train, test, plot. |
| **README.md**         | You’re reading it. |

---

## Quick notes on the data

* **Samples:** 1 , 797 pictures  
* **Classes:** digits **0‑9** (fairly balanced)  
* **Features:** 64 grayscale values (flattened 8×8 image)  

That’s small enough that K‑NN runs in a blink, but still big enough to see real patterns.

---

## How I ran things (tiny cheat‑sheet)

```bash
# 1. set up environment (once)
python -m venv venv
source venv/bin/activate  # Win: venv\Scripts\activate
pip install pandas scikit-learn matplotlib jupyter

# 2. fire up the notebook
jupyter notebook knn_digits.ipynb
Inside the notebook I:

Loaded the Excel file into a DataFrame.

Scaled everything to 0‑1 with MinMaxScaler() (helps K‑NN a lot).

Split 75 % train / 25 % test.

Looped over k = 1, 3, 5, 7, 9 and printed accuracies.

Drew a confusion matrix for the best k (usually 3).

Used PCA down to 2‑D just to sketch the decision regions (purely for eye‑candy).

Typical test accuracy: ≈ 98 % with k=3.

