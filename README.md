# Movie Review Sentiment Analysis

## Project Overview
This project focuses on classifying movie reviews as either **positive (1)** or **negative (0)**.  
The dataset is structured in a Kaggle competition format with separate training and test sets.  
The task is to build a text classification model that predicts sentiment for unseen reviews.

## Data Source
The dataset is from the Kaggle challenge: **"Py-Sphere Movie Review Sentiment Challenge"**.
the data set link : https://www.kaggle.com/competitions/py-sphere-movie-review-sentiment-challenge/data

- The **training set** contains movie reviews with sentiment labels.  
- The **test set** contains only reviews without labels, which are used for final prediction.  

## Workflow
The project followed a structured workflow covering all steps of the data science lifecycle:

### 1. Data loading  
The training and test datasets were loaded using pandas.  
Basic inspection of shapes and columns confirmed the dataset was consistent with the challenge requirements.  

### 2. Exploratory analysis  
Initial exploration was performed to check class balance, review lengths, and the presence of missing values.  
This gave a quick understanding of whether the dataset was balanced and helped anticipate preprocessing needs.  

### 3. Text preprocessing  
A cleaning function was created to remove HTML tags, URLs, non-alphabetic characters, and extra spaces.  
All text was converted to lowercase for consistency.  
This step ensured the text was in a uniform format before feature extraction.  

### 4. Feature extraction  
TF-IDF vectorization was applied to transform the cleaned reviews into numerical features.  
The vocabulary was limited to 1000 features, and English stopwords were removed to focus on more meaningful words.  

### 5. Baseline model  
A simple baseline was established by predicting the majority class for all reviews.  
This provided a reference accuracy that the trained models needed to outperform.  

### 6. Model training  
Two classical machine learning models were trained: **Logistic Regression** and **Multinomial Naive Bayes**.  
Logistic Regression was trained with regularization to avoid overfitting, while Naive Bayes was tested as it is a common choice for text classification.  

### 7. Model evaluation  
Both models were evaluated on a validation set using accuracy, classification reports, and confusion matrices.  
This step showed not only which model performed better but also how well each handled the two sentiment classes.  

### 8. Cross-validation  
Cross-validation with five folds was used to check the consistency of the best model.  
This gave a more reliable estimate of performance and ensured the results were not dependent on a single train-test split.  

### 9. Final training  
After identifying the best model, it was retrained on the full training dataset to take advantage of all available labeled data.  

### 10. Test prediction and submission  
The final model was applied to the test dataset, and predictions were generated.  
These predictions were saved into `submission.csv` in the exact format required by Kaggle.  

## Results
- The best-performing model was **Logistic Regression** with regularization parameter `C=0.1`.  
- Logistic Regression achieved higher validation accuracy compared to Naive Bayes.  
- Cross-validation showed consistent performance across folds, confirming model reliability.  
- Final predictions were generated for the test set and saved in `submission.csv`.  

## Conclusion
The project demonstrates a complete sentiment analysis pipeline using classical machine learning methods.  
Logistic Regression proved to be more effective than Naive Bayes for this dataset.  
The workflow covers text preprocessing, feature extraction, model comparison, evaluation, and submission.  
