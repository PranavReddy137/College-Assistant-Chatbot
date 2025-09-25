# College-Assistant-Chatbot
This is an AI-powered chatbot designed to assist visitors navigating the college website. The chatbot answers questions related to college departments, faculty, courses, campus facilities, and more. It helps new users find the information they need in an intuitive and interactive way.
## Features

- **Interactive Conversations**: Users can ask questions about departments, courses, faculty, and campus facilities.
- **Real-Time Response**: The bot responds with high confidence based on predefined intents.
- **User-Friendly Interface**: The chatbot can be integrated into a college website to assist new visitors in navigating the content effortlessly.
- **Customizable**: You can add new intents, modify existing responses, and retrain the model based on updated data.

## Technologies Used

- **Python**: Programming language used to implement the chatbot.
- **PyTorch**: Deep learning framework used for training the chatbot model.
- **NLTK**: Natural Language Processing toolkit used for tokenizing, stemming, and preprocessing text data.
- **JSON**: Used for storing the intents and responses in a structured format.
- **Neural Networks**: The core model used for classifying user input and generating responses.

## How It Works

### 1. Training the Model
The chatbot is trained using a dataset stored in the `intents.json` file. Each intent consists of several user input patterns and corresponding bot responses. The training script (`train.py`) processes these patterns into bag-of-words vectors, which are then used to train a simple feedforward neural network model to classify the user’s query.

### 2. Text Preprocessing (`nltk_utils.py`)
The `nltk_utils.py` file provides utility functions for preprocessing the user’s input text:
- **Tokenize**: Breaks down a sentence into individual words or tokens.
- **Stem**: Reduces each word to its root form (e.g., "running" becomes "run").
- **Bag of Words**: Converts a sentence into a numerical vector indicating the presence or absence of words from a predefined list.

### 3. Neural Network Model (`model.py`)
The model used in this chatbot is a simple neural network with:
- **Input Layer**: Takes the bag-of-words representation of the sentence.
- **Hidden Layers**: Two hidden layers that use ReLU (Rectified Linear Unit) activation functions.
- **Output Layer**: Predicts the most likely intent from a set of predefined categories.

The model is trained using **cross-entropy loss** and the **Adam optimizer**.

### 4. Bot Interaction (`chat.py`)
- **Input**: The user inputs a query in the terminal.
- **Processing**: The input is tokenized, stemmed, and converted into a bag-of-words representation.
- **Prediction**: The neural network predicts the intent, and the bot responds with a random response from the matching intent's predefined responses.

## File Structure

The project consists of the following files:

- `chat.py`: The script that runs the chatbot and interacts with the trained model.
- `train.py`: The script that trains the neural network model using the data from `intents.json`.
- `model.py`: Defines the architecture of the neural network.
- `nltk_utils.py`: Contains functions for tokenization, stemming, and creating the bag-of-words representation.
- `intents.json`: Contains the intents, patterns, and responses used to train the model.
- `data.pth`: The trained model saved after training.
