Link to model weights: https://drive.google.com/file/d/1vbBWxGgiQ6xGHjGG4StVFZqPwVrLAjkr/view?usp=share_link

Link to data set: https://drive.google.com/file/d/11hxph-2Dj3qGJTDV1yj5GCfSxtEaHdCs/view?usp=share_link

Workflow

1. Import required libraries: Import necessary libraries and load the dataset into a pandas dataframe.
2. Data preprocessing: Preprocess the text data using the TextVectorization layer and split it into training, validation, and testing sets.
3. Model building and training: Create a Sequential model with an Embedding layer, LSTM layer, and Dense layers. Compile and train the model on the training and validation sets.
4. Prediction and visualization: Define a function to predict toxicity labels for an input comment, format the results, and create a bar chart of category probabilities. Integrate this function with a Gradio interface for interactive use.

Data Preprocessing

1. Read in the dataset from a CSV file using pandas and separate the input text (X) and corresponding labels (y) for classification.
2. Initialize a TextVectorization layer and adapt it to the data. This layer will preprocess the text data and vectorize it.
3. Set the output sequence length to the maximum sequence length, which is the maximum number of words in any comment in the dataset.
4. Shuffle, batch, and prefetch the dataset for efficient training.

Model Building and Training

1. Build a Sequential model with an Embedding layer, a Bidirectional LSTM layer, and several dense layers.
2. Compile the model with the BinaryCrossentropy loss function and Adam optimizer.
3. Train the model on the training set and evaluate it on the validation set.
4. Load the trained model.

Prediction and Visualization

1. Define a score_comment function to predict toxicity labels for an input comment, vectorize the comment, and obtain predictions. Format the results as a string.
2. Modify the function to return a bar chart of category probabilities using matplotlib.
3. Define a Gradio interface that allows users to enter a comment, choose a toxicity category, and input a custom phrase or word (optional). The output of the interface is an image of the bar chart showing the category probabilities.
4. Launch the Gradio interface for interactive use.
