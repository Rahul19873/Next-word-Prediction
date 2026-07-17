# Next Word Predictor (Shakespeare's Hamlet)

## Project Overview
This project demonstrates a simple Next Word Predictor built using a Long Short-Term Memory (LSTM) Recurrent Neural Network. The model is trained on the text of William Shakespeare's 'Hamlet' to predict the most probable next word given a sequence of preceding words. The trained model is then deployed as an interactive web application using Streamlit.

## Features
-   **Data Loading and Preprocessing:** Utilizes NLTK to load text, Tokenizer for word tokenization, and padding for sequence preparation.
-   **LSTM Neural Network:** Implements a deep learning model with Embedding, LSTM, and Dense layers for sequence prediction.
-   **Model Training:** Trains the model to learn word sequences and predict subsequent words.
-   **Interactive Web Application:** A Streamlit application allows users to input text and receive real-time next word predictions.
-   **Model Persistence:** Saves the trained model and tokenizer for easy deployment.

## Technologies Used
-   **Python**
-   **TensorFlow / Keras:** For building and training the neural network.
-   **NLTK:** For text data loading from `gutenberg` corpus.
-   **NumPy:** For numerical operations, especially with padded sequences.
-   **Streamlit:** For creating the interactive web user interface.
-   **Pandas (optional, for initial data exploration/handling)**

## Setup and Installation

### 1. Clone the Repository
```bash
git clone <your-repository-url>
cd <your-repository-name>
2. Install Dependencies
It's recommended to use a virtual environment.

pip install -r requirements.txt
(You'll need to create a requirements.txt file from your Colab notebook, e.g., pip freeze > requirements.txt).

Key dependencies include:

tensorflow
keras
nltk
numpy
streamlit
scikit-learn (for train_test_split)
pandas (if used for initial data loading/inspection)
pyngrok (for exposing Streamlit in environments like Google Colab)
3. Data Preparation (if running locally without Colab)
This project uses Shakespeare's Hamlet from NLTK's gutenberg corpus. The Colab notebook handles downloading and saving this as shakespeare-hamlet.txt.

How to Run the Project (Google Colab)
This project was developed in Google Colab. The notebook (next_word_predictor.ipynb) contains all the steps from data loading to model training and Streamlit app generation.

Open the Colab Notebook: Upload or open next_word_predictor.ipynb in Google Colab.

Run All Cells: Execute all cells in the notebook sequentially.

Launch Streamlit App: The notebook includes cells to create app.py and then run it using streamlit run app.py. It also includes instructions for using pyngrok to get a public URL for the Streamlit app.

# Example Colab commands to run the Streamlit app
!pip install streamlit pyngrok
# ... (cell to create app.py)
!streamlit run app.py &>/dev/null&
from pyngrok import ngrok
public_url = ngrok.connect(8501)
print(f"Streamlit App URL: {public_url}")
How to Run the Project (Locally)
Train the Model: Run the Python script that trains the model and saves next_word_lstm.h5 and tokenizer.pickle. (In a real-world scenario, you'd have a separate train.py script. For this project, you would adapt the notebook cells to a script.)
Launch Streamlit App: Ensure next_word_lstm.h5 and tokenizer.pickle are in the same directory as app.py.
streamlit run app.py
Open your web browser and navigate to the address provided by Streamlit (usually http://localhost:8501).
Usage
Once the Streamlit application is running, you can:

Enter any sequence of words in the input text box.
Click the "Predict Next Word" button.
The application will display the model's predicted next word.
Model Details
The model is a sequential Keras model:

Embedding Layer: Maps words to dense vectors.
LSTM Layers: Two LSTM layers learn long-term dependencies in the sequences.
Dropout Layer: Prevents overfitting during training.
Dense Output Layer: With softmax activation, outputs probabilities for each word in the vocabulary.
