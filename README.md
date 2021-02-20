# StumbleuponEvergreen

Neural Net approach to provide a solution.

Step 1: Analyse the data.
    I had a quick overview of the data. 
    Verified if the dataset is imbalanced. 
    Checked which of the metrics have an impact on the label.
    I find that the boilerplate to be impacting the label.
    
Step 2: Build a simple model and have a benchmark.
    Before moving further, I created a Neural Network with an embedding, a lstm and a dense layer.
    Fed the NN with Padded sequence with a basic tensorflow tokeniser.
    Ran the model for 50 epochs.
    Reached an accuracy of 63%.
    Needed to improve.

# The data is not that clean.

Step 3: Clean the boilerplate data.
    Remove punctuations, stopwords, numbers, nouns, delimiters etc.
    Map the words to their root words with Lemmatization.
    
Step 4: Train again but with cleaner data.
    I trained the same model with cleaner data for the same number of epochs.
    The accuracy climbed to 74%.
    Not bad... But can be better.
    
Step 5: Use Glove word embeddings.
    I used the 100d word embeddings of glove.
    Created embedding index and embedding matrix.
    And then passed it to the embedding layer of my model.
    Trained it again and the accuracy finally reached 76%.
    Wait what???
    
The model seemed to overfit to the train dataset. Needed to fix it.

Step 6: Tune those hyperparameters.
    I added Dropout layers after each layer and played with the percent of dropout.
    I added kernel regularization to the dense layer.
    I changed my optimizer from adam to sgd.
    
    Using sgd I had control over the learning rate.
    Finally at a learning rate of 0.01.
    Dropout of 0.6 at every layer.
    and a l2 of 0.01 regularisation.
    My model achieved 80.08 accuracy.
    
Step 7: Make predictions using the test dataset.
    Load and clean the test dataset.
    create and pad the sequences using the same tokeniser.
    Feed it to the model.
    Match the results with the urlid.
    Write the results to a csv name submit.csv.
    
    
There is still room for progress.
Maybe using BERT. 
    
This was a task for NLP intern. Using transformers didn't feel right.

However I'll upload the BERT with a few more tricks to improve soon.
    
    
