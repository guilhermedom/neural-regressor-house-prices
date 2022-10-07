# Neural Regressor House Prices

4-layer [fully connected neural network] on house price [linear regression].

---

## Problem Overview

House price prediction is a popular problem in the machine learning field. Many regressors using different techniques have been proposed to predict house prices based on house characteristics. Some of the base techniques include: [linear regression], [polynomial regression], [random forests], [neural networks], [K-Nearest Neighbors] and others.

Data quality and importance of features in house price datasets are questionable most of the times. So, it is important to select relevant variables to shape a model. However, some feature interactions are too subtle, even if the features seem straightforward. Some features themselves may not be important but the interaction they have with others may significantly boost a model's performance. This has been one of the challenges on working with house price datasets.

## Analysis Introduction

[Fully connected neural networks] can easily be adapted to work as regressors. They are, inherently, a combination of weighted sums before their activation function. If the selected activation function just outputs the weighted sum of the neurons from the previous layer, the neural network becomes a regressor. Following this notion, we decided to check the capabilities of a fully connected neural network to become a good linear regressor for house price data.

We build a 4-layer neural network and train it on a filtered version of our dataset, that has only the most significant features. We remove redundant features and features that have low correlation with the response variable, the house price. After fine-tuning our model with the best hyperparameters we could find, we achieved an adjusted R2 score of nearly 0.64. Even if it is a fine [R2 score], as it is far from a random R2 score of 0.0, it is far from the optimal R2 score of 1.0.

After training another model on the not filtered dataset, we noticed that the performance was not heavily compromised. A R2 score of 0.62 was achieved by this new model. Hence, we can say that there is not much to gain from feature selection. Our analysis also indicates that the response variable has an exponential behavior, meaning that our linear regression neural network will not be able to optimally predict it. In the next figure we see that our predicted prices grow linearly, while the actual prices grow exponentially.

![pred_vs_actual_neural_regressor_house_prices](https://user-images.githubusercontent.com/33037020/194449817-f7471202-697c-400a-af30-edce31be516d.PNG)

In spite of that, our first model, trained with selected features only, is able to represent the behavior of the response variable to some extent. The figure below shows the actual price curve, along with the curve predicted by our model, for a subsample of the testing data.

![pred_vs_actual_curves_neural_regressor_house_prices](https://user-images.githubusercontent.com/33037020/194449800-e21390dd-3535-4c43-a029-f5daac9041fd.PNG)

[//]: #

[linear regression]: <http://www.stat.yale.edu/Courses/1997-98/101/linreg.htm>
[our dataset]: <https://www.kaggle.com/datasets/shivachandel/kc-house-data>
[Fully connected neural networks]: <https://www.oreilly.com/library/view/tensorflow-for-deep/9781491980446/ch04.html>
[fully connected neural network]: <https://www.oreilly.com/library/view/tensorflow-for-deep/9781491980446/ch04.html>
[R2 score]: <https://en.wikipedia.org/wiki/Coefficient_of_determination>
[polynomial regression]: <https://online.stat.psu.edu/stat462/node/158/>
[random forests]: <https://link.springer.com/article/10.1023/A:1010933404324>
[neural networks]: <https://d2l.ai/chapter_linear-regression/index.html>
[K-Nearest Neighbors]: <https://www.ibm.com/topics/knn>
