# SMS/Email Spam Classifier

## Project Description

This project is an Email/SMS Spam Classifier built using Machine Learning. It utilizes Content-Based Filtering and Text Vectorization (TF-IDF) with a Multinomial Naive Bayes model to classify incoming messages as either Ham (Not Spam) or Spam. The classifier is exposed via a simple web interface.

## Main Features

- **Real-time Classification:** Allows instant prediction of whether a message is spam or not.
- **Text Preprocessing Pipeline:** Includes lowercasing, tokenization, special character removal, stop-word removal, and stemming (using NLTK's Porter Stemmer).
- **Persistent Model:** Uses pre-trained `model.pkl` and `vectorizer.pkl` files for fast prediction without retraining.
- **Web Interface:** Built using Streamlit for easy user interaction.

## ⚠️ Important Note About Model Files

> **Note:**
> The files `model.pkl` (trained Multinomial Naive Bayes model) and `vectorizer.pkl` (fitted TF-IDF object) are NOT included in this repository due to their large size.
>
> **Before running the app, you must generate these files:**
> 1. Ensure `spam.csv` (included in this repo) is in the root directory.
> 2. Open the `main.ipynb` Jupyter Notebook.
> 3. Run all cells in the notebook.
> 4. This will generate `model.pkl` and `vectorizer.pkl` in your directory.

## Installation Instructions

### Prerequisites

- Python (version 3.x recommended)

### Setup

1. **Clone the repository**
    ```bash
    git clone [https://github.com/Vishwaa-P/sms-spam-classifier.git](https://github.com/Vishwaa-P/sms-spam-classifier.git)
    cd sms-spam-classifier
    ```

2. **Install the necessary Python libraries**
    ```bash
    pip install streamlit numpy pandas scikit-learn nltk
    ```

3. **Download NLTK resources required for tokenization and stop-word removal**
   Run once in a Python environment:
    ```python
    import nltk
    nltk.download('punkt')
    nltk.download('stopwords')
    ```

4. **Verify Model Files**
    Ensure that `model.pkl` and `vectorizer.pkl` have been generated (see "Important Note" above) and are in the root directory.

## Usage Instructions

The project is run via the command line using Streamlit, which launches the web interface.

**Command:**
Navigate to the project's root directory and run:
```bash
streamlit run app.py
