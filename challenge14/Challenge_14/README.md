# Machine Learning Trading Bot

In this application, I assume the role of a financial advisor at a top financial advisory firm. My firm would like me to improve the existing algorithmic trading systems and mantain the firm's competitve advantage in the market. To do so, I'll enhance the existing trading signals with machine learning algorithms that can adapt to new data.

---  

## Overview

My first step is to establish a baseline performance. To begin, I import the OHLCV dataset into a Pandas Dataframe. Then, I generate trading signals using short- and long-window SMA values. I split the data into training and testing datasets and use the SVC classifier method to fit the training data and make predictions on the testing data. With the prediction finished, I generate a classification report and create a Dataframe for my predictions.
I then create a cumulative return plot that shows the actual returns vs. the strategy returns. This will serve as my baseline against which to compare the effects of tuning the trading algorithm. The objective is to tune the algorithm to give my firm optimal returns.

![screenshot of the baseline model](https://raw.githubusercontent.com/chaimkriger/Challenge_14/main/4-100-3%20orignal%20svm%20(2).png)

This is my baseline algorithm. As you can see above, the strategy returns are clearly greater than the actual returns. Meaning, it would be more profitable for my firm to use the baseline trading algorithm than to simply hold the equity. Attached below is the classification report for this model.

![screenshot of classification report of baseline model](https://raw.githubusercontent.com/chaimkriger/Challenge_14/main/SVM%20Testing%20Report%20(2).png)

Although the trading algorithm is clearly giving positive returns, my firm wants me to better the parameters for the algorithm with some tuning.

My next step is to change the amount of months for the trading period. The baseline model used a training period of 3 months, and so I attempt to run the algorithm with a training period of 6 months. Below is my results:

![screeshots of 6 month model returns](https://raw.githubusercontent.com/chaimkriger/Challenge_14/main/svm%204-100-6%20returns.png)

As you can see, the returns of the tuned model is greater than the baseline
model. When training the data for 6 months, the recall of the model is also improved by 2 points, as you can see below:

![screeshot of 6 month classification report](https://raw.githubusercontent.com/chaimkriger/Challenge_14/main/svm%204-100-6-%20report.png)

Now that I've attempted to tune the model by changing the training period, I will now attempt to tweak the SMA input features.  
To find the optimal parameters to use for my model, I created a function to run my parameters through, which allowed me to find the optimal short- and fast-window, and the optimal training period that will net the greatest returns. After running the function, I found that a short-window of 5, a long-window of 150, and a training period of 8 months gives me cumulative returns of 2.07! Below are the screenshots of the strategy returns overlayed with the actual returns, and the classification report:

![screenshot of optimal algorithm](https://raw.githubusercontent.com/chaimkriger/Challenge_14/main/SVM%20Optimal%20Algorithm.png)
![screeshot of classification report](https://raw.githubusercontent.com/chaimkriger/Challenge_14/main/SVM%20Optimal%20Classification%20Report.png)

As you can see, I've clearly found parameters that will greatly boost my algorithm's efficiency. I'm sure my firm will love the fine tuning that I have done for the algorithm.

My next step is to evaluate a new machine learning classifier. I will use the original parameters that was provided, but I will be applying them to the performance of a second machine learning model. I import LogisticRegression as my second model. Using the original training data as the baseline model, I fit another model with the new classifier. 
Below are the results of my second model, which were not really that impressive to say the least:

![screenshot of LOGREG returns](https://raw.githubusercontent.com/chaimkriger/Challenge_14/main/LOGREG%20returns%20original.png)
![screenshot of LOGREG report](https://raw.githubusercontent.com/chaimkriger/Challenge_14/main/LGR%20Testing%20report%20(2).png)

As you can see above, when I tryed to use a different model, my strategy returns turned negative, which is definetly not what my firm is going for. And if the returns were worse than my baseline model, they were definetly worse than my tuned model.

To summarize, I have found that the algorithm works best when programmed with a short-window of 5, a long window of 150, and a training period of 8 months. This is with the SVC model.

---  

## Technologies

This project leverages Python 3.7.

---

## Installation Guide

Before running this application, Python must be installed.

---

## Usage

Simply run the code to view the different models I have created. You can change any of the models to your preference, to see if you can get a higher accuracy score.

---

## Contributors

Just me, and a little bit of help from module 14

## License

No license, feel free to copy the code any time.











