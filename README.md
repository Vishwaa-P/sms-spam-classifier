# SMS/Email Spam Classifier

## Project Description

This project is an Email/SMS Spam Classifier built using Machine Learning. It utilizes Content-Based Filtering and Text Vectorization (TF-IDF) with a Multinomial Naive Bayes model to classify incoming messages as either Ham (Not Spam) or Spam. The classifier is exposed via a simple web interface.

## Main Features

- **Real-time Classification:** Allows instant prediction of whether a message is spam or not.
- **Text Preprocessing Pipeline:** Includes lowercasing, tokenization, special character removal, stop-word removal, and stemming (using NLTK's Porter Stemmer).
- **Persistent Model:** Uses pre-trained `model.pkl` and `vectorizer.pkl` files for fast prediction without retraining.
- **Web Interface:** Built using Streamlit for easy user interaction.

## Important Note About Model Files

> **Note:**  
> The files `model.pkl` (trained Multinomial Naive Bayes model) and `vectorizer.pkl` (fitted TF-IDF object) are NOT included in this repository due to their large size.  
>
> If you wish to use or retrain the model:
> - You can train your own classifier using the [Kaggle SMS Spam Collection Dataset](https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset) and the scripts provided in this repository.
> - Once you have trained your model and vectorizer, save them as `model.pkl` and `vectorizer.pkl` in the root directory.
> - Alternatively, contact the project maintainer for pre-trained files, if available.

## Installation Instructions

### Prerequisites

- Python (version 3.x recommended)

### Setup

1. **Clone the repository**
    ```bash
    git clone https://github.com/Vishwaa-P/sms-spam-classifier.git
    cd sms-spam-classifier
    ```

2. **Install the necessary Python libraries**
    ```bash
    pip install streamlit pickle numpy pandas scikit-learn nltk
    ```

3. **Download NLTK resources required for tokenization and stop-word removal**  
   Run once in a Python environment:
    ```python
    import nltk
    nltk.download('punkt')
    nltk.download('stopwords')
    ```

4. **Place your trained model files in the root directory**
    - `model.pkl`
    - `vectorizer.pkl`

## Usage Instructions

The project is run via the command line using Streamlit, which launches the web interface.

**Command:**  
Navigate to the project's root directory and run:
```bash
streamlit run app.py
```

**Interaction:**  
The application will open in your web browser, where you can paste the text message into the input box and click the **Predict** button.

## Example Input/Output

| Input Message                                                         | Expected Output              |
|-----------------------------------------------------------------------|------------------------------|
| Free entry in a competition to win $1000! Text 'WIN' to 87121 now.    | Spam (Predicted as 1)        |
| Hey, how are you doing? Let's catch up later this week.               | Not Spam (Predicted as 0)    |

## Technologies Used

- **Language:** Python
- **Machine Learning Libraries:** Scikit-learn (Multinomial Naive Bayes, TfidfVectorizer), NLTK (text preprocessing)
- **Web Framework:** Streamlit
- **Data Handling:** Pandas, Numpy

## Attribution / License

- **Dataset Source:** [spam.csv from Kaggle](https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset)
- **License:** _To be chosen (MIT or Apache 2.0 are recommended for open source)_

