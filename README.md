# Data_Incubator
Proposed project for data incubator

Proposal Abstract
Machine learning and artificial intelligence have become more and more important in almost every area of our lives. Tools developed in machine learning academic research have found their way in many applications of various industries including financial industry. For example, text-mining integrated with machine learning algorithms has been demonstrated to be very helpful in predicting the stock movement [1]. Here I would like to proposal a text-mining system for market-prediction that can improve the performance of investment in stock markets. 

1.	Text-mining for market-prediction
The general workflow of market-prediction using text mining techniques is as follows: Textual data from social media, news and blogs is feed into a prediction system, which will output the prediction on market movement after processing input data and doing some calculations. 
In the following part of this proposal, I will go through each piece of the generic common system of text-mining for market-prediction and select data-set or method to use to build an effective stock return forecast system. 

2. Different parts of text-mining for market-prediction system
•	Textual data
Most of the text-mining for market-prediction systems are using financial news since it is less noisy compared with general news. Headlines of financial news are argued to be more effective than body of news since they are deemed to be more straightforward. On the other hand, social media has been playing more and more important role in people’s investment decision. For example, twitter from a political lead could drive the market in one way or another. 
In this proposal, I will use a decade of New York Times front-page stories, combined with Financial Times and Bloomberg as my textual data source. The data source can be extended to include company annual reports and press releases.  
•	Market data
The investment universe of this proposal is stocks in S&P500 since they are in general very liquid to trade. One can also narrow down the stock list to a set of large high-tech companies, such as Google, Apple, and Amazon. Tech companies are sensitive to downturns of business cycle, which is around the corner. 
•	Feature-selection
The most common feature selection technique is “bag-of-words” which breaks the text into its words and consider each of them as a feature. Word sequence and syntactic structures are ignored in this technique. The main drawback of doing so is that the order and co-occurrence of words, which contains lots of information of the text, are lost. Some advanced techniques have been proposed in academic research, for example, “n-grams”. “n-grams” is a contiguous sequence of text, which preserves some of the syntactic structures and word sequence [2]. 
In this proposal, I will use “n-grams” as the feature-selection method.
•	Dimensionality-reduction
For a large text document, feature-selection in text could yield a very large number of features which can decrease the efficiency of the learning algorithms. In this proposal, I will set a minimum and maximum occurrence limits and select terms that reach a number of occurrences in between. I will also perform other common dimensionality-reduction procedures, such as features stemming, punctuation removal and removal of stop-words. 
•	Feature-representation
Once the set of features is determined, each feature needs to be transformed in to a value to be processed by machine learning algorithms.
In this proposal, I will use Term Frequency-Inverse Document Frequency (TF-IDF) to represent features. TF-IDF is the ratio of term frequency in the document over document frequency of that term in all our documents [2]. High TF-IDF is reached when we have high term frequency in the given document and the low document frequency of the term in the whole collection of documents, which is precisely the idea that we want to follow. 
•	Machine-learning algorithms
Support Vector Machine (SVM) and k-Nearest Neighbors (k-NN) are common classification techniques used in machine learning. SVM has been successfully used in textual classification [2, 4], while k-NN is rarely considered in text-mining context. 
In this proposal, I will use both SVM and k-NN as textual classification methods and compare their performance after.
•	Other issues
Some other issues should also be taken into consideration.
1. Fixed or sliding time-window on training data: I will use sliding window on training data which ends up right before the time window of testing data to make sure the learning algorithms capture up-to-date information.
2. Whether or not to include technical signals of stock movement in data source: Some researcher has demonstrated that technical signals could improve the performance in text-mining [4, 5]. So I will include technical signals, for example moving average of stock price, in the dataset.

3.  Summary
In this proposal, I introduce the general text-mining for market-prediction system and break it into different parts and select one or two proper methods to deal with each one of them to enhance the performance of market-prediction. Data source is designated, along with detailed data-preprocessing and training models. Future work includes the evaluation of proposed system using available data and integrate more advanced machine learning algorithms into the system.  


Reference:
1, Nassirtoussi et al., “Text mining for market prediction: A systematic review”. Expert Systems With Applications, 41 (2014).
2, Hagenau et al., “Automated news reading: Stock price prediction based on financial news using context-capturing features”. Decision Support Systems, 55, 685-697 (2013).
3, Tasci and Gungor, “Comparison of text feature selection policies and using an adaptive framework”. Expert Systems with Applications, 40 (2013).
4, Schumaker and Chen, “Textual analysis of stock market prediction using breaking financial news”, ACM Transactions of Information Systems, 27, 1-19 (2009). 
5, Schumaker et al., “Evaluating sentiment in financial news articles”. Decision Support Systems, (2012).

