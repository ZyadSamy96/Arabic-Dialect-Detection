# Arabic-Dialect-Detection
Many countries speak Arabic; however, each country has its own dialect, the aim of this project is to build a model that predicts the dialect given the text.

# Prroject Steps:
#### 1- Data Preprocessing
- Removed the following:
- All mentions. 
- URLs.
- Non-word characters and punctuation.
- Arabic stopwords. (For the ML model only.)
- Arabic diacritics.
- Elongations.
- Digits.

#### 2- Model Building and selection 
- TF-IDF Model
Tried both Count Vectorizer and TF-IDF feature extractors and used TF-IDF as it produced better results.
Trained an SVM model on the data extracted by TF-IDF and joined both the feature extractor and the model in a pipeline.

- Deep Learning Model 
Trained GRU and LSTM bidirectional models with 2 layers and GRU produced better accuracy (~80%).
Used a maximum sequence length of 60 for the GRU model which fully captures most instances of the data, and 67 for the LSTM model which is the maximum length of all instances.
Extracted and indexed all unique words in the corpus which are around 240k words.
Used context vectors and embedding vectors of size 128.

#### 3- Deployment
- Deployed the model using Flask with Python with an HTML template file.
- Used the simple machine learning model for deployment as it had better performance and accuracy, also it produced better results on some testing sentences.

![image](https://github.com/ZyadSamy96/Arabic-Dialect-Detection/assets/94635686/03384fb2-bf65-4cf2-a5b5-9a6fd944a984)

