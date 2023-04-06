Link to model weights: https://drive.google.com/file/d/1vbBWxGgiQ6xGHjGG4StVFZqPwVrLAjkr/view?usp=share_link
Link to data set: https://drive.google.com/file/d/11hxph-2Dj3qGJTDV1yj5GCfSxtEaHdCs/view?usp=share_link

Workflow

The required libraries are imported and the dataset is loaded into a pandas dataframe.
The comment_text column is assigned to the X variable and the target labels are assigned to the y variable.
The TextVectorization layer is used to preprocess the text data.
The data is split into training, validation, and testing sets.
A Sequential model with an Embedding layer, LSTM layer, and Dense layers is created and compiled.
The model is trained on the training and validation sets, and the metrics are recorded in the history variable.
The model is used to predict the toxicity labels for a given comment.
The predicted results are formatted and returned as a string.
The function is modified to also return a visual output of the category probabilities as a bar chart.
The function is integrated into a Gradio interface that allows users to enter a comment and choose a category and custom phrase/word (optional).
The output of the interface is an image of the bar chart showing the category probabilities.

Data Preprocessing

Read in the CSV file containing the dataset using pandas.
Assign the 'comment_text' column from the dataframe (df) to X, and the target labels (all columns from index 2 to the end) to y. This separates the input text and the corresponding labels for classification.
Initialize a TextVectorization layer, adapt it to the data, and vectorize the input text.
Define a vocabulary and index the words in the vocabulary.
Initialize the TextVectorization layer again, adapt it to the data, and set the output sequence length to the maximum sequence length. The maximum sequence length is the maximum number of words in any comment in the dataset.
Shuffle, batch, and prefetch the dataset.

Model Building and Training

Build a Sequential model with an Embedding layer, a Bidirectional LSTM layer, and several dense layers.
Compile the model with the BinaryCrossentropy loss function and Adam optimizer.
Train the model on the training set and evaluate it on the validation set.
Load the trained model.

Prediction and Visualization

Define a function to predict toxicity labels for an input comment, vectorize the comment, get predictions, and format the results as a string.
Define another function to predict toxicity labels and return a bar chart of category probabilities.
Define an interface using the gradio library, allowing users to input a comment, choose a toxicity category, and input a custom phrase or word.
Launch the interface.
