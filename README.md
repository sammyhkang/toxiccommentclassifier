This model detects and highlights toxic content in user-generated comments using a deep learning architecture, combining an Embedding layer, Bidirectional LSTM layer, and Dense layers for multi-category toxicity classification. It allows users to visualize toxic words within the text, aiding content moderation and identifying areas for guidance. The model incorporates a Gradio interface for user interaction, enabling users to input comments, visualize highlighted toxic words, and add custom categories for additional content identification, making it a valuable tool for various text analysis and moderation tasks.

1. Workflow

Import required libraries: Import necessary libraries and load the dataset into a pandas dataframe.
Data preprocessing: Preprocess the text data using the TextVectorization layer, split it into training, validation, and testing sets, and create TensorFlow datasets.
Model building, training, and evaluation: Create a Sequential model with an Embedding layer, Bidirectional LSTM layer, and Dense layers. Compile, train, and evaluate the model on the training, validation, and test sets.
Highlight toxic words: Define a function to highlight toxic words in a comment based on the model's predictions and custom categories.
Gradio interface and interaction: Create and launch a Gradio interface for scoring comments using the model, highlight toxic words, and display custom categories.

2. Data Preprocessing

Read in the dataset from a CSV file using pandas and separate the input text (X) and corresponding labels (y) for classification.
Initialize a TextVectorization layer and adapt it to the data. This layer will preprocess the text data and vectorize it.
Split the dataset into training, validation, and testing sets.
Create TensorFlow datasets from the train, validation, and test sets for efficient training.

3. Model Building, Training, and Evaluation

Build a Sequential model with an Embedding layer, a Bidirectional LSTM layer, and several Dense layers.
Compile the model with the BinaryCrossentropy loss function, Adam optimizer, and relevant metrics.
Train the model on the training set and evaluate it on the validation and test sets using early stopping and batch history callbacks.
Save and load the trained model.

4. Highlight Toxic Words

Define a function to highlight toxic words in a comment based on the model's predictions and custom categories.
Define a score_comment function to predict toxicity labels for an input comment, vectorize the comment, obtain predictions, and highlight toxic words.
Define a function to get custom categories and their corresponding words or phrases from the user.

5. Gradio Interface and Interaction

Define a function to create a Gradio interface for scoring comments using the model.
Plot the training loss and accuracy for each epoch.
Launch the Gradio interface for interactive use, allowing users to enter comments and visualize the highlighted toxic words and custom categories.
