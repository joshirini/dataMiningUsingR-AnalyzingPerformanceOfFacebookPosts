# dataMiningUsingR-AnalyzingPerformanceOfFacebookPosts

1.	Executive Summary:
Social media is on its way to become the most important channel for brand recognition. 85% of marketers using social media are unsure of how to use it. Thus, our project revolves around using various data mining techniques to predict the performance metrics of the posts published on Facebook. We analyzed how each of the seven input features (Page total likes, Type, Category, Post Month, Post Weekday, Post Hour, Paid) affect the impact of the post and we found out that performance variables comment, share, and like had the most influence by the given input features.
 
2.	Data source: 
Our data set was sourced from “UCI Machine Learning Repository”, the UCI Machine Learning Repository is a collection of databases, domain theories, and data generators that are used by the machine learning community for the empirical analysis of machine learning algorithms. Below is the hyperlink to the dataset: 
https://archive.ics.uci.edu/ml/datasets/Facebook+metrics 
 
3.	Dataset Description:
The data set consists of performance metrics of posts published on a cosmetic brand’s Facebook page in the year 2014. We split the dataset in 70 (training):30 (testing) ratio. The data set consists of 19 columns described as below:
 
Sample size: n = 500 records
3.1	Independent variables: The total number of independent variables are 7 listed as follows:
•	Page total likes
•	Type
•	Category
•	Post Month
•	Post Weekday
•	Post Hour
•	Paid

3.2	Dependent variables: The total number of dependent variables are 12 dependent variables mentioned as follow:
•	Lifetime post total reach
•	Lifetime post total impressions
•	Lifetime engaged users
•	Lifetime post consumers
•	Lifetime post consumptions
•	Lifetime post impressions by people who liked Facebook page
•	Lifetime post reach by people who liked Facebook page (unique users)
•	Lifetime people who liked page and engaged with the post
•	Comment
•	Like
•	Share
•	Total Interactions (Sum of comment, like, and share)
 
3.3	Sample Observations:
Below is the snapshot of some 13 observations from the dataset.
The first entry in the first snapshot shows that the page had 137177 likes when the page was posted. The post is of type “status”, classified under “inspiration” category. It was posted on a “Thursday (5)” in the month of “November (11)” at 02:00 hours. It is an “unpaid” post (0). 6692 unique users saw the post. The post has 13092 impressions out of which 7549 impressions (number of time people saw the page whether clicked or not) are from people who liked the page. Out of those 7549 impressions, 3336 were unique. Similarly, the next snapshot shows entries of other 7 dependent variables. 
  
4.	Why is this data of interest?
The dataset gives an insight on how the performance variables (like, comment, lifetime total reach, etc.) varies with respect to the independent variables mentioned above. Our main aim is to implement models that predicts the performance variables which is nothing but the impact of the posts. Using this prediction, manager can decide whether to publish a post or not.

5.	Methodology
We explored the following regression based models to model the 12 performance metrics individually. 
1.	Linear Regression
2.	k-Nearest Neighbours
3.	Regression Trees
To find which performance metrics were being predicted well across all the models, we used the following error measures to compare the results of each of the 12 models for each modeling technique. 
RMSE: root-mean-square error
AE: Average Error
MAE: mean absolute error
Once we were able to narrow down on whicthe specific Tableau was used to perform exploratory analysis
5.1	Linear Regression
We performed Linear regression as a straightforward approach to train and consequently predict the quantitative response for our 12 dependent variables.
Given below are the performance evaluation metrics for them:
 
Total Interactions (a composite dependent variable; summation of number of comments, likes and shares) has the lowest RMSE.

5.2	Regression Tree
We ran 12 regression trees for each of the 12 dependent variables against the 7 independent variables (See Appendix). 
For all the models we calculated the performance measures which can be seen below:
 
Models with dependent variables ‘Comment’, ‘Like’, ‘Share’, ‘Total Interactions’ tend to perform better than the other models. This led us to decide upon the most relevant dependent variables which are namely ‘Comment’, ‘Like’, ‘Share’, ‘Total Interactions’. 
Considering the relative relevance and importance of these dependent variables, we delve further into explaining these four regression trees.

Taking a cumulative view at our regression trees we conclude that best hours to post to are 5,19,21 and 23, the best months are Feb, May, August and September and the best days are Sunday, Tuesday, Wednesday and Friday. This is to a great extend in coherence with our other models and exploratory analysis that we performed on tableau. Based on these statistics a manager can decide which hour, month and day of the week will likely be most suitable in terms of likes, comments, shares and total interactions. 

Business Perspective 
There is a saying used by many, often attributed to entrepreneur George Bradt, that states, "People don't buy products, they buy brands,". The phenomenon of social media has taken the world by storm and now online market presence has become a necessity.  
If you’re doing it right, social media will lead to real relationship building; with already existing customers and also turn prospective consumers into buyers. 
But what defines right?
According to one report by Social Media Examiner, 85 percent of marketers who use social media aren’t clear on which social media tools would work best for their business. While our analysis does not determine the content of the post, it illustrates the type and timing of the facebook posts that users are most receptive towards. Essentially, prediction of evolution of a post allows social media managers of the company to decide the ideal medium and timing for the post to garner maximum attention. Attention is determined through the number of interactions and engagements. The impressions statistics are derived from the number of times the post was loaded onto to the user’s browser. And engagements are variables that define actual user interaction feedback; such as comments, likes, shares, etc. While the post maybe available on the viewer’s homepage, it is highly likely the user scrolled through without noticing the post. Hence, we can say engagements are real determinants of the user’s interest in the post. 
Amongst our 12 models developed for each dependent variables, prediction accuracy was highest for shares, followed by comments and likes. The results of these models are of maximum use as they will help forecast the popularity of each post. 
As per our analysis, the main decisive factor was the type of post, namely status, photo and video); with photo taking the first slot. Category was next in line amongst the causal factors followed by timing of the post. The prioritising of these influencers helps social media marketing  analysts to post so as to maximise impact.
 
Future Recommendations
This research project primarily focused on modeling performance metrics (dependant variables) extracted from facebook posts of a company’s Facebook page using regression models through which we were able to identify the most important performance metric to monitor using some key features identified. However, this research is not the end as this does not provide an end-to-end predictive model that a company can use to evaluate its social media performance. With this project as a baseline, several ideas arise for future research.
1.	Refine Model: Our project is no exception to the saying that, no model is ever perfect and there is always some scope for improvement. While our project was based on the research done in (S.Moro et all,2016), this project produced fresh results with some different insights as compared to it. Hence, using our results as the baseline, the models used can be refined further to reduce the RMSE (using boosting) or experiment with different models (using neural networks). This can help build a more robust predictive model for total interactions.
2.	Move up the conversion funnel: With a certain level of confidence in the predictions of total interactions, we can now use its correlation with various dependent variables to predict them by converting total interactions as an independent variable of the dataset. While the number of interactions represent potential conversions on the company website, we want to also be able to predict metrics from the top of the funnel as they reflect on the overall awareness of the brand. Predicting those metrics would help companies digital marketing strategies to improve on their post impressions reach which in turn can increase the number of total interactions of the post.
3.	Text Mining: As the scope of this project, the dataset we worked on for this project was already aggregated and did not contain the actual text of the posts. However, it would be an interesting area for future research to mine the topics of the facebook using text mining models like LDA posts to create a predictive model for the topics to include in a post. This would help companies focus on creating posts that are guaranteed to attract larger attention on social media.
4.	Revenue Model: A new tangent for research would be to create a predictive model for generating the Return on Investment of a post before it is actually posted. This however would involve developing a revenue model based on some existing/past data which we currently do not possess. A highly conceptual model with based on market statistics would be a long shot, but would make the research quite extensive and strenuous.
