# Ind_Project_New-Topic-Analysis-Classification--Kaggle

## Summary
I worked with the News Category Dataset, which provided a headline and description, etc. in .json format.  I created a dataframe, focused the data on the headline text, and began to engineer features using the NLTK library for NLP.  I tokenized and then lemmatized the words in each headline based on all possible parts of speech built into the lemmatizer Class.  For each lemmatized word, I used NLTK again to display the part of speech in order to concatenate this to the words-- this provided different features for the times when the same word (by spelling) was used in a different way (e.g., roll as a noun vs. roll as a verb).  I used two different vectorizers, Tf-Idf, and Count, and created different sparse matrices for each based on a split of the full data for training/validation and testing.  I used several classifiers to train on the data, using GridSearchCV for initial cross-validation and parameter tuning, and scored it on the testing set, picking the "best" (based on accuracy score on the testing set) of this group for additional hyperparameter tuning and vectorization iterations as well. I used this best model to predict the category of a few different recent headlines.  

## Results
### Models Utilized
I trained and evaluated several classifiers: Multinomial Naive Bayes, Decision Tree, Random Forest, and AdaBoost.  

### Scores
The best score on the training and testing sets came from the Multinomial Naive Bayes Classifier and utilzied the CountVectorizer.  Initial training yielded parameters and score were:
  - Best Model Parameters: {'alpha': 1.0, 'class_prior': None, 'fit_prior': True, 'force_alpha': 'warn'}
  - Best Test Score: 0.61
  - Best Vectorizer: CountVectorizer(analyzer='char_wb', min_df=2, ngram_range=(2, 5))

After additional iterations on the model parameters and vectorizer parametetrs, the model only improved slightly on the testing set:
  - Best Model Parameters: {'alpha': 1.0, 'class_prior': None, 'fit_prior': True, 'force_alpha': 'warn'}
  - Best Test Score: 0.622
  - Best Count Vectorizer: CountVectorizer(analyzer='char_wb', min_df=2, ngram_range=(4, 6))
  - Best Count Vectorizer min_df: 2
  - Best Count Vectorizer ngram_range: (4, 6)

## Skills (Developed & Applied)
Programming, Python, Statistics, Numpy, Pandas, Dataframes, JSON, Natural Language Processing, NLP, Lemmatization, NLTK, Classification, Supervised-ML, Scikit-learn, Hyperparameter tuning, Model evaluation, Model refinement
