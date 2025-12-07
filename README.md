# ✈️ Automated Survey Analysis Tool (Airline Sentiment)

## 🚀 Project Overview
In the age of social media, companies receive thousands of customer comments daily. Manually analyzing this data is slow, expensive, and prone to human bias.

This project builds an **Automated Sentiment Analysis Tool** using **Deep Learning (Natural Language Processing)**. It processes unstructured text data (tweets/surveys) from customers and automatically classifies them as **Positive**, **Neutral**, or **Negative**. This allows Product and Customer Success teams to instantly gauge public perception and identify pain points without reading every single message.

## 📊 Key Features & Capabilities
* **Automated Text Classification:** Converts raw text into actionable sentiment insights using NLP.
* **Context Awareness:** Utilizes **Bidirectional LSTMs (Long Short-Term Memory)** networks to understand the context of words (e.g., distinguishing "not bad" from "bad").
* **Real-World Generalization:** The model includes regularization techniques (Dropout, L2) to ensure it performs well on unseen data, not just training data.
* **Custom Inference Engine:** Includes a function to test specific, user-written reviews in real-time.

## 🛠️ Technologies Used
* **Deep Learning:** TensorFlow, Keras (Sequential API, Embedding, LSTM)
* **Language:** Python 3.x
* **Data Processing:** Pandas, NumPy, Scikit-Learn (Label Encoding, Train-Test Split)
* **Text Preprocessing:** Tokenizer, Pad Sequences
* **Visualization:** Matplotlib (Accuracy/Loss curves)

## 📂 Dataset
The project utilizes the **Twitter US Airline Sentiment** dataset.
* **Source:** Public GitHub Repository
* **Content:** Thousands of tweets directed at major US airlines (United, Virgin America, Southwest, etc.).
* **Columns:** `text` (the customer feedback) and `airline_sentiment` (the target label).

## ⚙️ Methodology

1.  **Data Ingestion & Cleaning:**
    * Loaded raw CSV data directly from source.
    * Filtered dataset to focus on relevant text and sentiment columns.
    * Encoded string labels (Positive/Neutral/Negative) into numerical integers using `LabelEncoder`.

2.  **Natural Language Processing (NLP) Pipeline:**
    * **Tokenization:** Converted words into a dictionary of integers (Vocab size: 5,000 words).
    * **Padding:** Standardized all sentences to a fixed length (50 words) to ensure uniform input for the neural network.

3.  **Model Architecture (Bi-LSTM):**
    * **Embedding Layer:** Maps words to dense vectors to capture semantic meaning.
    * **Bidirectional LSTM Layers:** Two layers (64 & 32 units) processing text in both forward and backward directions to capture full context.
    * **Regularization:** Applied **Dropout (0.3)** and **L2 Regularization** to prevent overfitting.
    * **Output Layer:** Softmax activation for multi-class probability distribution.

4.  **Training Strategy:**
    * **Optimizer:** Adam
    * **Loss Function:** Sparse Categorical Crossentropy
    * **Callback:** Implemented `EarlyStopping` to halt training automatically when validation loss stabilizes, preventing overfitting.

## 📈 Results & Performance
The model demonstrates a strong ability to distinguish between sentiment classes.

* **Training Accuracy:** High convergence showing the model successfully learned language patterns.
* **Real-World Testing:**
    * *Input:* "The flight was on time and the staff was polite." -> **Prediction: Positive** ✅
    * *Input:* "I waited for 3 hours and lost my luggage." -> **Prediction: Negative** ✅



---
*This project highlights the use of AI to automate business processes and improve customer experience analytics.*
