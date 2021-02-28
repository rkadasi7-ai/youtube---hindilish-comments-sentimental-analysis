# youtube---hindilish-comments-sentimental-analysis
Abstract: As we know YouTube has become the biggest and most widely used social media platform, in which people use it for entertainment purpose, study purpose, sports ,news,etc. Our goal is to create a communication between the channel creator and a subscriber. Viewers can express their opinions, suggestions and emotion in the comment section. Through our analysis the channel owner would be able to know what the viewers are expecting from them, so that they utilize this information and use it  for increasing their views. For such analysis we selected a top two  Indian cookery channels of India namely KABITHA‘s kitchen and NISHA MADULIKHA ‘s Kitchen. These two channels contain hinglish comments, we are going to perform sentimental analysis on hinglish comments. Two featuring techniques called count vectorizer and TFIDF vectorizer were used, and a number of parametric and non-parametric machine learning models were applied on two datasets with the two vectorizers. Logistic regression with  count vectorizer gave an accuracy of 77.4% on kabitha’s kitchen dataset and Nisha’s kitchen dataset gave an accuracy of 76.4% . Every classifier was statically tested and implemented. 
Keywords: sentimental analysis, machine learning, hinglish, cookery channels. 

III METHODOLOGY
 
In this section sentimental analysis is followed by the application of machine learning models. 

Data gathering: The data was taken from the top two cookery you tube channels kabithas’s kitchen and nisha’s Madhulika's kitchen , the data was extracted from you tube API by or supervisor and It was handed over to me. Each comments were  manually labeled into 7 labels below. 

1) label 1: gratitude 
            	This label of comments contains people who express their gratitude after watching the video. For example bahuth danyavad, tanqu so much aunty, your video was very helpful etc. 
2)label 2: About recipe  
           	In this label of comments contain people who talk about recipe whether the recipe is good or bad. Example : yein recipe bahuth tasty Hain, yuuuumyy, I love all your recipies etc 
3)label 3: About video 
            	In this label of comments contain people who talk about the video quality like whether the video is too length or too short or the clarity of the video.  
Example : acha video hain, nice video. 
4)label 4: Praising  
       	In this label of comments contain people who praise the chef , viewers express appreciation towards the chef. 
Example: ur great mam, the best cook etc. 

5)label 5: hybrid 
      In this label of comments contain the comments which are combination of gratitude and admiration of the cheff. 
Example: hello mam your really great ,thanq u for ur recipies 
 
 
6) label 6: undefined  
             	In this label of comments contain the comments which are not related to any of the above categories. 
7) label 7: (suggestions or queries) 
           	In this label of comments contain people who ask suggesions or queries regarded to the recipe 
Example: chilly kaa quantity kitna dalu . 

Data preprocessing:
The two datasets were with noisy data with punctuations, upper case letters emojis symbols, stop words etc. , these types of text are to be removed because they are of no use moreover, these texts text slow down the performance of the machine learning models. Removal of such things is done in this phase called data preprocessing, it means that preparing the data in a clean and a proper format data for the implementation of the models. This process involves removal of puncuation , if the data contains {,.} should be removed  the next step is to convert the upper case letters into lower case letters because the models assume that the upper case letter and the lower case letter are different. Then the next step is stemming, in this process the words like go,going,gone will all be considered as one. The next step is tokenization, in this stage the data is splitted intotokens.Removing the stop words is not an easy task because there is no inbuilt stop words list for hinglish  like English. So we created  manually a hinglish stop words list even though it wasn't enough but we managed with them to the extent. The stop words list contains like words such as {hain,aap,aapke …} , after removal of stop words , puncuations , numbers the clean data is converted into a corpus. 

Even though we are implementing the machine learning models , the models cannot directly deal with the text data , so this is one of the important stage of this process this where the data is converted into certain features for the implementation of machine learning algorithms. 

In our case we used vectorizers to convert the corpus data  into vectors we used the count vectorizer and the TFIDF vectorizer. 

Count vectorizer: This vectorizer creates a matrix  with terms and cells which represent the count of each token and display in the matrix. So what is the meaning of this matrix is that as number of occurrences of each token is display it shows the importance of the feature. 

TFIDF vectorizer :  
From the above approach we know that it counts the number of occurrences but this vectorizer states that high frequency is alone not enough the weight of the frequency is also required. The tfidf gives the score with term frequency dividend into subsequent terms by quantity of terms. 

Building the machine learning model  
             We used the supervised machine learning models, the supervised machine learning models are categorized into parametric and non-parametric models, difference between the parametric and non-parametric is that the parametric has limited features where as non-parametric has infinite features. As the training data increases the number of features of non-parametric algorithms increases. The examples of parametric models are logistic regression, naive bayes, SVM etc. On the other hand, non-parametric models examples are random forest, decision tree etc. Any way we are going to apply both the parametric models. 
 
Before applying the training  set to model , the traing set was prepared to perform cross validation which was performed with 10k folds cross validation. 10 k folds cross validation is which the training set is divided into 10 parts one of them will be treated as test set and validation is performed on the training set for every 10 parts of the set. Then the avg accuracy of the cross validated training set is cross verified with the general accuracy obtaining if the training set is high  then the model is said to be overfitted I, else if the  traing set accuracy is low then it is said to be underfitted. 

For the validation of the model performance we used accuracy,precison,f1 score, mathews corelated coefficient precision score , recall score. 

The results of the both the datasets after applying machine learning algorithms with two vectorizers count and tfidf vectorizers are shown in the below tables. 
In the result table of kabitha’s kitchen dataset  logistic regression with the count vectorizer has obtained highest accuracy with 77.44 %, f1. Score of 77.3% ,precison of 76.28%and recall of 77.88%  among all the machine learning algorithms where as SVM with linear kernel using TFIDF vectorizer is close to the results of Logistic regression with an accuracy of 76.14%. 
Bernouli Navie bayes with count vectorizer has the lowest accuracy of 45.61% wheras bernouli navie bayes with tfidf vectorizer has the second least accuracy of 48.61. 

From results of the  nisha kitchen dataset we observe that SVM with linear kernel using tfidf vectorizer has a highest accuracy of 77.24, f1 score of 77.32, precision of 77.36 and recall of 77.94 among all the machine learning algorithms, where as logistic regression is close to SVM with an accuracy of 76.73%,f1 score of 74.95% , precision of 75.70% ,recall of 74.7%. Naïve bayes algorithm has the least accuracy compared other machine learning algorithm. 
