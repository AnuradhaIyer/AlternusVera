#  Alternus Vera - Team Seekers - Fake News Detection 


#### - Course Code: CMPE-257 
#### - Group name: Seekers


#### Business Problem

What is Fake News?

- The term ‘Fake news’ is mostly used to describe completely fabricated stories that is deliberately misleading.
- Fake News detection involves assessing the quality of the content given to understand whether what you are seeing is true or not.

Project objective:

The widespread propagation of false information online is not a recent phenomenon but its perceived impact in the 2016 U.S. presidential election has thrust the issue into the spotlight. Technology companies are already exploring machine learning-based approaches for solving the problem. In this project, we are using NLP based text classification to identify the different news categories.


#### Top Features Selected

Important Features identified from the Fake news article:

List of Factors identified by reading “Fake News Detection on Social Media: A Data Mining Perspective” 

1.  Political affiliation
2.  Sentimental Analysis
3.  Topic features – That can be extracted using models like LDA
4.  Post/Social media activities based: People express their emotions or opinions towards fake news through social media posts.
5.  Visual based: Fake news detection based on images and video links features in the dataset.
6.	Linguistic based: Fake news detection based on Sensationalism and writing style (features: Article title and text)
7.	Reliable source: Fake news detection based on the source of the article.
8.	Authenticity: Fake news includes false information that can be verified as such.
9.	Intent: Fake news is created with dishonest intention to mislead consumers
10.	Confirmation Bias: consumers prefer to receive information that confirms their existing views
11.	Psychology utility: receiving news that satisfies their prior opinions and social needs
12.	Social credibility: which means people are more likely to perceive a source as credible if others perceive the source is credible
13.	 Frequency heuristic: means that consumers may naturally favor information they hear frequently, even if its fake
14.	 Credibility and Reliability: based on registration age, number of followers/followees, number of tweets the uer has authored.
15.	 Stance features (also called viewpoints) – indicate the user’s opinion about the news such a supporting or denying. 
16.	 Credibility – for the posts access the degree of reliability
17.	 Echo Chamber – users on social media tend to form groups containing like-minded people where they then polarize their opinions, resulting in an echo chamber effect. 
18.	 Sensationalism 
19.	 Location / Geography 
20.	 Education 
21.	 Gender 
22.	 User based: malicious account, names, comments, likes.
23.	 Naive Realism: consumers tend to believe that their perceptions of reality are the only accurate views, while others who disagree are regarded as uninformed, irrational or biased.
24.	 Network based: users form different networks on social media in terms of interests, topics and relations. 
25.	 Style based: capturing the manipulators in the writing style of news content.
26.	 Short-term utility: the incentive to maximize profit, which is positively correlated with the number of consumers reached; 
27.	 Long term utility: their reputation in terms of news authenticity. Utility of consumers consists of two parts: (i)  Information utility: obtaining true and unbiased information (usually extra investment cost needed); 
(ii) Psychology utility: receiving news that satisfies their prior opinions and social needs, e.g., confirmation bias and prospect theory. 


#### Dataset used for the Project – Kaggle dataset for Fake news
https://www.kaggle.com/mrisdal/fake-news/version/1#fake.csv

The dataset considered for Alternus Vera project is “Getting real about fake news” from Kaggle. This dataset contains text and metadata from fake and biased news sources from the web. The data obtained was in csv file and contains 12999 samples. Each sample corresponds to a news article with text, title, author, language, type and many more features. 

The features or columns in the Kaggle fake news dataset are listed below:
- uuid - Unique identifier
- ord_in_thread – author of story
- published - date published
- title - title of the story
- text - text of story
- language - data from webhose.io
- crawled - date the story was archived
- site_url - site URL from BS detector
- country - data from webhose.io
- domain_rank - data from webhose.io
- thread_title
- spam_score - data from webhose.io
- main_img_url - image from story
- replies_count - number of replies
- participants_count - number of participants
- likes - number of Facebook likes
- comments - number of Facebook comments
- shares - number of Facebook shares
- type - type of website (label from BS detector)


## Important factors(topics) considered for the project and contributions:

<b>1. Political Affiliation - Ashwini Shankar Narayan <br />
2. Sentimental Analysis - Nidhi Jamar <br />
3. Topic features LDA - Anuradha Rajshekar <br />
4. Social media activities - Sindhu Goudru Shivanandappa Patil
</b>

### We Seekers, worked as team to,
-	Decide on the dataset – Kaggle’s Fake news dataset
-	Identify 4 important factors Political affiliation, Sentimental analysis, Linguistic based and Post based/ Social media activities based.
-	To enrich the data, tokenize, stemming and lemmatization on the text column in the fake news dataset, we used NLTK. Stemming and Lemmatization is done only for sentiment analysis and topic features factors.
-	To build the corpus, we used Gensim
-	To remove stop words, special characters, punctuation and to convert to lower case NLTK’s stop-word list is used.
-	For political affiliation and social media activities based, TF – IDF scores are used to calculate the cosine similarity between words in the text column of the dataset and the dictionary.
-	We have applied classification algorithms like Logistic Regression, Naïve Bayes and Random Forest twice on the dataset. First time we applied to the original fake news dataset and again to the enriched fake news dataset i.e. along with the original features the dataset now has an extra feature named ‘Processed_text’ which is basically text column in the fake news dataset after removing stop words, special characters and punctuation.
- Ranked the articles based on different scores for different features
- Also, calculated the Percentage Of Truth for the articles after applying each classification algorithm. Our dataset contains various categories or types like ‘bias', 'conspiracy', 'fake', 'satire', 'hate', 'junksci' and 'state'. And each article belong to any one of the above types based on the highest weightage of the types. Percentage of truth of any article means how much percent of each of the above types is there in that specific article. For example, we have calculated the percentage of truth for the 0th article in the dataset and we have found that this article is [31% bias, 28.9% conspiracy, 1.1% fake, 7.5% satire, 16.7% hate, 6.9% junksci, 7.8% state].

# Conclusion

- The data science community is helping to fight against filtering out fake news from social media feeds and other resources with the help of AI.
- Detecting fake news is a classic example of text classification that helps in solving a problem: Can you build a model that can differentiate between “Real” news vs “Fake” news?
- The main goal of the project is to explore feature extraction process manually. Input to the project is a dataset from Kaggle the “Fake news dataset” and contains information about news, article and the type of news. 
- Applied distillation algorithms - Latent Dirichlet Allocation to get more insights and finally add this to the polynomial equation.
- The expected output is a polynomial equation representing topic’s weightage and its score per article. The score for Political affiliation, sentimental analysis, social media activities can help us determine accurately on the factors contributing to fake news.

    ##### Political_affiliation_weight *Political_affiliation_score +  Sentimental_analysis * Sentimental_analysis_score + Topic_modeling_weight * Topic_modeling_score + Social media_weight * Social media_score = Final Score

    ##### Plynomail Equation = 0.3* Sentimental_analysis_score + 0.2* Topic_modeling_score + 0.25* Social media_score + 0.25 * Political_affiliation_score 


- Applied three classification algorithms - Logistic Regression, Naive Bayes Classifier and Random Forest on the overall dataset.
- Calculated accuracy for the above classifications and constructed a confusion matrix.

We intend to understand the data and the process of converting data to numerical features, which in future can be fed to artificial neural networks to predict the type of news article.
