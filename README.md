# Hate Speech Detection

This project implements a Hate Speech Detection system using a Decision Tree Classifier. The model is trained on a dataset of tweets to classify them into three categories:

- Hate Speech
- Offensive Language
- No Hate and Offensive Language

The project also includes a web interface using Gradio for user interaction.

---

## Dataset

The dataset used in this project is a CSV file named `twitter.csv`. It contains tweets labeled as:
- `0`: Hate Speech
- `1`: Offensive Language
- `2`: No Hate and Offensive Language

The `labels` column is derived by mapping these values to the corresponding categories.

---

## Project Setup

### Dependencies

Ensure you have the following libraries installed:
- `numpy`
- `pandas`
- `sklearn`
- `nltk`
- `gradio`

If not installed, you can use the following commands to install them:
```bash
pip install numpy pandas scikit-learn nltk gradio
```

### Mount Google Drive

To access the dataset from your Google Drive, use:
```python
from google.colab import drive
drive.mount('/content/drive')
```

Place the `twitter.csv` file in the appropriate directory in your Google Drive.

---

## Preprocessing

The following preprocessing steps are applied to the text data:
1. Lowercasing the text.
2. Removing URLs, HTML tags, punctuation, and numerical values.
3. Removing stopwords using NLTK.
4. Stemming the words using NLTK's Snowball Stemmer.

---

## Model Training

The pipeline includes:
- Vectorizing the text data using `CountVectorizer`.
- Splitting the dataset into training and testing sets.
- Training a `DecisionTreeClassifier` on the training data.

### Metrics

The accuracy of the model is calculated using `accuracy_score` from `sklearn`.

---

## Interactive Interface

A Gradio interface is created for real-time predictions. Users can input a tweet, and the model will classify it into one of the three categories.

### Launching the Interface

The interface can be launched directly in the notebook with the following code:
```python
interface.launch(share=True)
```

---

## Usage

1. Run the notebook in Google Colab.
2. Mount your Google Drive and ensure the dataset is accessible.
3. Execute the cells to preprocess the data, train the model, and launch the Gradio interface.
4. Enter a tweet in the Gradio interface to check if it contains hate speech.

---

## Example

### Input
```plaintext
"This is an example tweet!"
```

### Output
```plaintext
"No Hate and Offensive"
```

---

## File Structure
```
Summer_Internship_Project.ipynb  # Jupyter Notebook for the project
twitter.csv                     # Dataset file located in Google Drive
```
