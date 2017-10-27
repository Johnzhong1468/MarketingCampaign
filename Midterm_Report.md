<h1 align="center">
Marketing Campaign Candidate Analysis Midterm Report 
</h1>
<h4 align="center">
Yiheng Xiao, Chen Zhong <br><br>
October 27, 2017
</h4>

### Project Introduction
Marketing campaign is essential for any business in any industry to grow customers and expand business. A successful company requires not only good product but also a good way to advertse its product. One of the most traditional yet effective way of marketing campaign is through phone calls. These phone-call based marketing campaigns are done by making phone calls to a pool of potential customers to promote certain products. Unfortunately, in order to increase the rate of success many potential customers will be called more than once. While it takes a lot of time and effort to attract a new customer, very often people will feel uncomfortable about the repetitive phone calls and may even jeopardize the campaigning company’s reputation.

The important question here is how to choose the pool of potential customer to increase success rate? If we can increase 
success rate of phone call marketing campaigns, less resource is required to attract each new customer and it is less likely 
to have negative adversiting effect.

Our approach to the problem is to analyze market campaign data, which includes information about the background of customers and try to 
determine the specific profile of customers who will be more likely to subscribe the product in campaign. More specifically, our project is to propose a data mining approach to select the best set of clients that are more likely to subscribe a product through telemarketing calls. 

### Data, Initial Processing and Visualization
* #### Raw Data
We selected the ["Bank Marketing Data Set"](http://archive.ics.uci.edu/ml/datasets/Bank+Marketing) from UCI Machine Learning repository. The data is taken from the direct marketing campaigns of a Portuguese banking institution (http://archive.ics.uci.edu/ml/datasets/Bank+Marketing). The marketing campaigns were based on phone calls. The data set consists of a list of 45211 samples with 20 features. We are interested in whether we can predict the "y" feature, which is the whether the particular sample subscribed to the product or not, using all other features given about that particular sample. Below is a list of sample important features:

| Bank Client data   | Description      |
|--------------------|:-----------------|
| age | age of clients, numeric |
| job | type of job, categorical |
| marital | marital status |
| education | level of education, categorical |
| default | whether has credit in default, categorical |
| housing | whether has housing loan, categorical |
| loan | whether has personal loan, categorical |


* #### Initial Data Cleaning
First thing we looked at was missing values. Besides the "poutcome" feature, most other features have similar amount of samples, to allow for initial steps, we filled the n/a values in "poutcome" with string "nonexistent" and proceeded to exclude all other n/a's, which result in a clean set of data with 30488 samples. We will try to preserve more data in the future. <br><br>
Since we are dealing with many categorical and binary attributes, we used one hot encoding for categorical features (each category as a new feature and has binary value), and we transformed binary attributes to {0,1}. Which expands the data set to having 54 features. Reason for one-hot-encoding is that regression analysis requires numerical values, and each category as a feature allows our models to compare the affect of each category independently and makes it easier for us to eliminate some of the features.

* #### Visualization
![plot](https://github.com/Johnzhong1468/MarketingCampaign/blob/master/3d_age_dur_pd.PNG)<br>
To First try to understand the data, we want to explore the relationship between some of the important features, here we chose age, duration of previous contact(duration), and number of days past after previous contact(pday). We also restricted the data to people who have been contacted more than once. People who accepted the product are color coded with blue and those who didn't are green. We can see that there are a lot of people that actually accepted the product under the condition that they were contatcted more than once. We can see that more samples have low duration and small pdays, and more samples are in the young age group than old age group. However for determining whether a sample accept the product, age does not seem to have a big effect graphically since "yes" samples have a similar profile as "no" sample. However duration and pday seem to have distinct affect, and we will explore that further in the future.

![plot](https://github.com/Johnzhong1468/MarketingCampaign/blob/master/age_dur_scatter.PNG)<br>
This plot shows the group of people who were only contacted once. We can see again that age has the same distribution profile among the "yes" and "no" group.

![plot](https://github.com/Johnzhong1468/MarketingCampaign/blob/master/age_dur_scat_shrt.PNG)<br>
We shrink duration to less than 150 and as expected people are likely to reject when the duration of the call is very short.

### Initial Model Selections



### Future Steps
* Preserve more data during the cleaning process. For example, treat n/a's as a new category and fill the gap.
* Eliminate some redundant features using lasso or other models.
* Explore the specific effect of particular features
* A more robust comparison of models

> #### 
