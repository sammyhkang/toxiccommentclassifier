This model detects and highlights toxic content in user-generated comments using a deep learning architecture, combining an Embedding layer, Bidirectional LSTM layer, and Dense layers for multi-category toxicity classification. It allows users to visualize toxic words within the text, aiding content moderation and identifying areas for guidance. The model incorporates a Gradio interface for user interaction, enabling users to input comments, visualize highlighted toxic words, and add custom categories for additional content identification, making it a valuable tool for various text analysis and moderation tasks.

Workflow

1. Import required libraries: Import necessary libraries and load the dataset into a pandas dataframe.
2. Data preprocessing: Preprocess the text data using the TextVectorization layer, split it into training, validation, and testing sets, and create TensorFlow datasets.
3. Model building, training, and evaluation: Create a Sequential model with an Embedding layer, Bidirectional LSTM layer, and Dense layers. Compile, train, and evaluate the model on the training, validation, and test sets.
4. Highlight toxic words: Define a function to highlight toxic words in a comment based on the model's predictions and custom categories.
5. Gradio interface and interaction: Create and launch a Gradio interface for scoring comments using the model, highlight toxic words, and display custom categories.

Data Preprocessing

1. Read in the dataset from a CSV file using pandas and separate the input text (X) and corresponding labels (y) for classification.
2. Initialize a TextVectorization layer and adapt it to the data. This layer will preprocess the text data and vectorize it.
3. Split the dataset into training, validation, and testing sets.
4. Create TensorFlow datasets from the train, validation, and test sets for efficient training.

Model Building, Training, and Evaluation

1. Build a Sequential model with an Embedding layer, a Bidirectional LSTM layer, and several Dense layers.
2. Compile the model with the BinaryCrossentropy loss function, Adam optimizer, and relevant metrics.
3. Train the model on the training set and evaluate it on the validation and test sets using early stopping and batch history callbacks.
4. Save and load the trained model.

Highlight Toxic Words

1. Define a function to highlight toxic words in a comment based on the model's predictions and custom categories.
2. Define a score_comment function to predict toxicity labels for an input comment, vectorize the comment, obtain predictions, and highlight toxic words.
3. Define a function to get custom categories and their corresponding words or phrases from the user.

Gradio Interface and Interaction

1. Define a function to create a Gradio interface for scoring comments using the model.
2. Plot the training loss and accuracy for each epoch.
3. Launch the Gradio interface for interactive use, allowing users to enter comments and visualize the highlighted toxic words and custom categories.
