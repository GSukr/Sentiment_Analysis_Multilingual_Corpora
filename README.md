# Sentiment_Analysis_Multilingual_Corpora
A generic approach to the supervised **sentiment analysis of social media content in foreign languages**.

The method proposes translating the documents from the original language to English with Google's Neural Translation Model. 
The resulted texts are then converted to vectors by averaging the vectorial representation of words. 
Testing the approach with several machine learning classifiers on Swedish, Polish, Slovenian and Croatian Twitter datasets returns up to 86% of classification accuracy on out-of-sample data.

Preprocessing steps include:
* data source: pre-labelled tweets in Croatian from [CLARIN.SI](https://www.clarin.si/repository/xmlui/). You can learn about the approach of the tweets annotation from [Mozetič, I., Grčar, M., & Smailović, J. (2016)](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0155036).
* translation: tweets are translated with Cloud Translation API in Python with google_api_translate library more: [Translate](https://pypi.org/project/google-api-translate/)
* data preprocessing: removing links, punctuation, digits, emojis and lowering the words.

The methodological set-up is as follows:

<img src=https://github.com/GSukr/Sentiment_Analysis_Multilingual_Corpora/blob/master/fig1.png width=350>


You can skip first 4 steps by using pre-calculated vectors: [vectors_croatian.csv](https://github.com/GSukr/Sentiment_Analysis_Multilingual_Corpora/blob/master/vectors_croatian.csv).

The results with different methods are as in the Table:

|model|accuracy	|time     |
|:----:| :----:  |  :----:|
|	DT	|0.749064	|0.887692 |
|	RF	|0.863296	|13.895610|
|	SVM	|0.861423	|11.448037|
|	KNN	|0.794007	|0.759187 |
|	LRM	|0.846442	|0.057601 |
|	ANN	|0.855805	|2.007087 |


The methodology is well explained in our paper: Galeshchuk S., Jourdan J., Qiu J. Sentiment Analysis for Multilingual Corpora. 2019. Accepted to the workshop of [ACL'2019](http://www.acl2019.org/EN/call-for-papers.xhtml).
Please cite if you use the method.

