## Libraries
- spaCy - "Industrial-Strength Natural Language Processing"
- pandas - "Python Data Analysis Library"
- scikit-learn - "Machine Learning in Python"


### Dictionary
- Lemmatization - A way for dealing with words that can be written in various ways, but have the same meaning
- Lemma - Root of word
- Stemming - A process of removing prefixes and suffixes to produce the simplest version of a word
- POS - Part of speech - Describes a words part within a scentence
- entity recognition - Identifying important elements (ex places, people, organizations, languages)
- Dependency Parsing - A technique to determine the meaning of a scentence by checking how words relate
- Word vector - A numeric representation of a word that communicates its relation to other words
- Text Classification - Add tags/categories to text according to content
- Logistic Regression
    - Borrowed from statistics
    - Common method for binary classification problems
- sentiment analysis
    - Classifying text into positive / negative
- BoW - Bag Of Words 
    - Converts text into a matrix of occurence of words within a document
    - It focuses on whether given words occurred or not in the document
    - It generates a matrix that we might see referred to as a BoW matrix or a document term matrix
    - Use CountVectorizer (from scikit-learn) to produce a BoW matrix
- N-grams 
    - Combination of adjactent words in a given text
    - N means the number of words thats included in the tokens
    - Unigram - Single words ("who", "will")
    - Bigrams - Two continious words ("who will")
- TF-IDF - Term Frequency-Inverse Document Frequency
    - A way of representing how important a term is within a document
    - A way of normalizing BoW by looking at each words frequency in comparison to the document frequency
    - The higher TF-IDF, the more important term within document
    - We can use scikit-lears TfidfVectorizer
- Hashing Vectorizer
    - Convert a text to a matrix of ocurrences
- Hashing Trick
    - [Introducing One of the Best Hacks in Machine Learning: the Hashing Trick](https://medium.com/value-stream-design/introducing-one-of-the-best-hacks-in-machine-learning-the-hashing-trick-bf6a9c8af18f)

- Noun - Identifies an object
- Adjective - Describes an object
- Verb - Describes an action


## Links
- [x] [https://www.dataquest.io/blog/tutorial-text-classification-in-python-using-spacy/](https://www.dataquest.io/blog/tutorial-text-classification-in-python-using-spacy/)
- [ ] [Text Classification A Comprehensive Guide to Classifying Text with Machine Learning](https://monkeylearn.com/text-classification/)
- [ ] [Logistic Regression for Machine Learning](Logistic Regression for Machine Learning)
- [ ] https://github.com/machinelearningmindset/machine-learning-course/blob/master/README.rst


## Books
- | ] [Deep learning with Python](https://www.manning.com/books/deep-learning-with-python)
