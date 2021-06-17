---
title: "The Relationship Between Bias, Variance, Overfitting & Generalisation in Machine Learning Models"
published: True
---
The tradeoff between bias and variance plagues every machine learning model. To better understand it, let’s consider 2 models that have fitted to a training data set.

![visualising high and low bias in training](/assets/article_images/bias-variance-overfitting-generalisation/high and low bias training.png){: class="blog-img"}


Here, we can see the linear regression model (straight line) not capturing the “true” relationship of the training set all too well whilst the other model (squiggly line) captures it perfectly. Since <b>bias</b> is defined as the inability for a machine learning model to capture the true relationship of the data, we can say that the straight line has high bias and the squiggly line has low bias.

To assess our claims, we can quantitively compare how well each model fits the training set by calculating their sum of squares.

![visualising high and low bias in training](/assets/article_images/bias-variance-overfitting-generalisation/sum of squares training.png){: class="blog-img"}

All we are doing here is measuring the distances from the fitted lines to each data point, squaring the values and summing them. We square them so that the negative distances don’t cancel out the positive distances.

In this instance, the squiggly line results in a sum of squares score of 0, indicating that it perfectly represents the relationship. So when comparing each model’s performance on the training set, the squiggly line wins!

So do we now just call it a day and deploy the squiggly line? No. A useful machine learning model should achieve good performance on unseen data i.e a testing data set! As such, let’s calculate each models sum of squares on a testing set.

![visualising sum of squares on testing set](/assets/article_images/bias-variance-overfitting-generalisation/sum of squares testing.png){: class="blog-img"}

When comparing each model’s sum of squares score on the testing set, the straight line wins. Strange right? To get more insight, let’s compare each models’ performance on both data sets, starting with the squiggly line.

![visualising high variance with squiggly line](/assets/article_images/bias-variance-overfitting-generalisation/squiggly line variance.png){: class="blog-img"}

So even though the squiggly line did a great job of fitting the training set, it did a terrible job of fitting the testing set. This difference in fits between data sets is called <b>variance</b>.

With definition of bias and variance in mind, we can see that the squiggly line has low bias since it’s flexible and adapts well to the training set but high variance since it results in very different sums of squares for different data sets. This means it is hard to predict how well the squiggly line will perform on different data sets.

Now let’s compare the straight line’s performance on both data sets.

![visualising low variance with straight line](/assets/article_images/bias-variance-overfitting-generalisation/straight line variance.png){: class="blog-img"}

On the contrary, the straight line has high bias since it is less flexible and does not adapt well to the training set but low variance since it results in a very similar sum of squares for different data sets. This means it is much easier to predict how well the straight line will perform on different data sets.

<h4>This is the trade-off between bias and variance.</h4>

A model thats fits the training set well but testing set poorly is said to be <b>overfit</b> to the training set and a model that fits both sets poorly is said to be <b>underfit.</b>

![visualising underfitting, overfitting and balanced fit](/assets/article_images/bias-variance-overfitting-generalisation/overfitting underfitting and sweet spot.png){: class="blog-img"}

Ideally in machine learning want a model that has low bias so it accurately models the “true” relationship in the training set, and has low variability so it produces consistent performance on different data sets. <b>Regularisation</b> techniques are used to help models find the sweet-spot between bias and variance.

The term used to describe a model’s ability to accurately capture the relationship of unseen data is called <b>generalisation</b>. A machine learning model’s ability to generalise is central to its success.

Given this significance, let’s investigate how well the models shown above generalise to the testing set.

![visualising generalisation](/assets/article_images/bias-variance-overfitting-generalisation/generalisation.png){: class="blog-img"}

We can see that the slightly curved line generalises the best to the testing set, thus would be the best model out of the 3 for this problem.
Generalisation is something us humans do exceptionally well but our computer friends do poorly. The more general a model is, the wider range of tasks it can accomplish and in turn the fewer models we need to build!

The human brain is the most general “model” we know of. For example, humans can recognise objects in many different lighting and weather conditions, whereas machine learning models really struggle with this. This capability definitely has something to do with our brains malleable construction. The term for this is <b>neuroplasticity</b>, which refers to the ability of neural networks in our brain to change and adapt as a result of experience i.e data. The superiority of the brain comes as no surprise given the incomprehensible amount of time mother nature has been optimising it for survival: current best estimates are ~521 million years.

With this in mind, it becomes less ironic that Artificial Neural Networks (ANN’s), which aim to mimic the human brain, are the current best machine learning models which have achieved state of the art results across many problem domains.

Although ANN’s are definitely still subject to the bias vs variance trade-off, their underlying structure enables many nifty regularisation methods to be built that facilitate in finding the sweet spot between bias and variance, thus improving their ability to generalise to unseen data. Many of these methods have also been slightly modified in order to enable ANN’s to calibrate uncertainty estimations about their predictions, which is an essential for real-world applications: especially those that are safety critical!

A few popular methods that I will be discussing in future articles are: Ensembling, Monte-Carlo Dropout and Stochastic Weight Averaging Gaussian.

If you are interested, feel free to explore my other <a href="https://joekadi.medium.com/">writing</a>, connect with me on <a href="https://www.linkedin.com/in/joe-kadi/">LinkedIn</a>, and subscribe to my <a href="https://mailchi.mp/e5e63e1cd43f/joe-kadi">mailing list</a> to be notified when I post!
