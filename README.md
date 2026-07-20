# AI-Enhanced Authorship Identification System
 An AI-enhanced authorship attribution system that identifies the author of a text among registered human and AI authors using stylometric analysis with TF-IDF-weighted character and word n-grams and a linear SVM. The system supports open-set authorship by recognizing unknown authors and allows new authors to be registered through similarity-based matching.

---

## Features

- Identifies the author of a text from a set of registered human and AI authors.
- Uses stylometric analysis based on character and word n-grams.
- TF-IDF feature extraction for representing writing style.
- Linear SVM classifier for multi-class authorship attribution.
- Detects unknown authors using confidence thresholding.
- Supports registration of new authors using cosine similarity.
- Model persistence using Joblib.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- SciPy
- Joblib
- Kaggle API

---

## Datasets

This project uses publicly available datasets.

### Human Authors
- Blog Authorship Corpus
(Texts of 40 different human authors)
### AI Authors
- LLM Detect AI Generated Text Dataset (Kaggle)
(Texts of 10 AI pseudo authors)
To keep the repository lightweight and comply with dataset licensing, the datasets are **not included** in this repository.

---

## Installation

Clone the repository:

```bash
git clone https://github.com/your-username/AI-Enhanced-Authorship-Attribution.git
cd AI-Enhanced-Authorship-Attribution
```

Install the required packages:

```bash
pip install -r requirements.txt
```

Configure your Kaggle API credentials before downloading the datasets.

---

## Methodology

1. Load and preprocess human- and AI-authored datasets.
2. Balance the dataset by selecting an equal number of samples per author.
3. Extract stylometric features using:
   - Character n-grams (3–5)
   - Word n-grams (1–2)
4. Apply TF-IDF weighting.
5. Combine feature vectors.
6. Train a Linear Support Vector Machine (SVM).
7. Evaluate the classifier using accuracy and classification metrics.
8. Detect unknown authors using confidence thresholding.
9. Register new authors using cosine similarity.

---

## Project Structure

```
AI-Enhanced-Authorship-Attribution/
│
├── README.md
├── requirements.txt
├── authorship_attribution.ipynb
├── docs/
│   └── Project_Report.pdf
└── models/
```

---

## Results

The system successfully performs multi-class authorship attribution across both human and AI authors while extending traditional authorship attribution through:

- Open-set author recognition
- Unknown author detection
- Incremental author registration
- When tested, the top-1 accuracy rate turned out to be 46% and top-3 accuracy of 73%

---

## Challenges

- New authors registered with a very limited text makes it difficult to grasp the writing style and results in inaccuracy
- Writing style of the same author can have variations depending on individual mood and the topic of writing, for example, the same author can have very distinct writing styles when writing about electrical circuits and existentialism
  
- - **Closed-set classifier**
  - The SVM classifier is trained only on the authors present in the training dataset. Newly registered authors are identified through similarity matching rather than being incorporated into the trained model, which may limit classification performance.

---

## Future Improvements

- Replace handcrafted stylometric features with transformer-based embeddings.
- Support incremental retraining after author registration.
- Develop a graphical/web interface.
- Improve performance on shorter texts.
- Evaluate additional machine learning and deep learning models.

---

## Project Report

A detailed description of the methodology, experimental design, and implementation can be found in **docs/Project_Report.pdf**.

---

## References

Misini, A., Kadriu, A., & Canhasi, E. (2022). *A Survey on Authorship Analysis Tasks and Techniques*. SEEU Review, 17(2).

---

## Disclaimer

This project was completed as part of a university group assignment. The repository documents the implementation and methodology of the system for educational and research purposes.
