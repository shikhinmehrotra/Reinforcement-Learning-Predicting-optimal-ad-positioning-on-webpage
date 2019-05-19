# Reinforcement-Learning-Predicting-optimal-ad-positioning-on-webpage
In this project, policy iteration, Q learning and Monte Carlo based methods are used to find the optimal placing of an ad on a website.

Placement of ads on website is the primary problem for companies that operate on ad revenue. The position where the ad is placed plays pivotal role on whether or not the ad will be clicked. Here we have the following choices:

Place them randomly, or
Place the ad on the same position
The problem with placing the ad on the same position is the user, after a certain time, will start ignoring the space since he's used to seeing ad at the place, he will end up ignoring that particular position hereafter. Hence, this will reduce the number of clicks on ads. The problem with the former option, placing them randomly, is it wouldn't take optimal positions into consideration. For instance, text beside images are viewed higher number of times than those text which are placed at a distance. It is infeasible to go through every website and repeat the procedure.

Using Reinforcement Learning we can approximate the human behavior.

# Why Reinforcement learning?
We cannot use traditional Machine Learning here, since it requires:

Huge data
Features
Tuning of many hyperparameters
And we neither have huge data, nor features. The only data we have is the position of the banner/ad and whether or not it was clicked. We will use this dataset from Kaggle: https://www.kaggle.com/akram24/ads-ctr-optimisation. We will solve this problem using both model-based (Policy iteration) and model-free methods(Q-Learning & Monte-Carlo). We'll simplify some assumptions for model-based technique.

# Data set
Our environment will be the dataset. It contains 10 ads position per row having values either 1, when the ad is clicked, or 0 when it is not. Every row can be considered as a state in the space, considering it kind of a navigation across multiple pages (on website, for instance) Lets load the dataset and visualize the first few rows.

state = webpage
action = placing the ad at any of the 10 positions on a webpage
reward = +1 if the ad was clicked at the position; else 0
Transition Probability: next webpage that user will end up in is random; therefore, it is 1/(total_webpages -1)

# Model building and evaluation
Three models are built using policy iteration method, Q learning and monte carlo. To test their performance, convergence plots are drawn and total rewards collected are noted. 

Q learning and policy iteration are both able to collect a total of 7424 rewards as compared to 1541 total rewards collected by monte carlo based method.
