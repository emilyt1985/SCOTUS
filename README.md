# [SCOTUS](https://emilyt1985.github.io/index.html)

## Case predictor based on Supreme Court makeup. Training a model based on data from court rulings from 1949 to 2017. 


### Project Objectives

As a group we wanted to build and train a model that would use existing judicial rulings of the Supreme Court and potentially predict future rulings as well as understand how the current Court would have ruled on historic cases.

Our data source is via Washington University Law (Cases Organized by Supreme Court Citation).
We focused our model training and predictions to Term, Precedent Alteration, Issue Area, Law Type, Case State Origin for justices Kennedy, Scalia, Thomas, Ginsburg, Beryer, Roberts, Alito, Sotomayor, Kagan, and Gorsuch (1991 -2017).

Tools utilized:

Data Cleanup and Organization: Python & Jupyter Notebook 
Model Construction: Sci-Kit Learn & Jupyter Notebook 
Model Used: Linear SVM 
Visualizations: Tableau

### Project Challenges

#### Objection(s)!
The greatest difficulty we faced was our rudimental knowledge of complex legalese. Some legal concepts proved challenging to interpret and contextualize.

#### Reimagined Expectations
Our initial objective was to predict cases where the Court has yet to hear oral arguments. Given that the most recent term has just ended, and the next term's case agenda is currently in process of being determined, we decided to focus our predictions on a selection of cases from the most recent term (2018), as well as some historic landmark cases - looking to see how the 2017 Court would have ruled on cases that have fundamentally shaped our lives.

#### Trial and Error
Finding a model that fit all justices proved challenging. We tried several (including Linear SVM, Random Forest, Voting Classifier Hard, Voting Classifier Soft, Logistic Regression, and Naive Bayes). In the end, we chose a model that best fit for all justices - Linear SVM.

#### Recuse me?
The human factor was pervasive in our dataset. Few things about the Supreme Court could be classified as black and white, or binary. Issue area, for one, is subjective. A case argued in front of the Court could have many parts in many issue areas. It's as broad as it is limiting. 

Thousands of parties petition the Court each year. Cases need a 4/9 vote to be heard. The Court typically only hears oral arguments on about 80 cases. Often, denying a case implies siding with the lower Court’s ruling. These cases could not be factored into the model. 

Theories of Constitutional Interpretation (often viewed as ‘liberal’ or ‘conservative’) can be as challenging to navigate as religious sects. 

Much of an individual Justice's constitutional interpretation involves willingness to rule against precedent. This isn’t a factor that can be measured or coded as ‘liberal’ or ‘conservative’.

We also have no way of knowing why a Justice didn't vote on a case. Though it's usually because they have recused themselves, there can be other reasons. These recuslas present yet another, unmeasurable factor in our model.

### Project Conclusions

The model we created was able to more closely predict current (2018 term) cases than historical cases. Much of that would be attributed to the makeup of the current court and general increasing polarity. The remainder can be blamed on the general challenge of human unpredictability. Part of the reason the Court was designed and appointed by our nation's founders was the need for humans to interpret our governing laws. Lastly, the nature of 'conservatism' and 'liberalism' have shifted over time, making current cases likely easier to predict since the model was trained with current data. 

Ideally, we would like to have a more complete model, trained for all Supreme Court rulings and Justices. Also, with a more current dataset we would like to be able to make predictions on cases the court has yet to hear in order to see how our model stands up.


### How to Train Your Model
![model](https://github.com/emilyt1985/emilyt1985.github.io/blob/master/images/giphy.gif)

After we selected the useful columns and cleaned up the NAN values in the original data, 
we did one-hot encoding to all the factors we used to predict a justice's ruling behavior:

![one](https://github.com/emilyt1985/emilyt1985.github.io/blob/master/images/1.png)


In our ML model, first we did data pre-processing, focusing on the direction of the individual justice's ruling:

![two](https://github.com/emilyt1985/emilyt1985.github.io/blob/master/images/2.png)


![three](https://github.com/emilyt1985/emilyt1985.github.io/blob/master/images/3.png)


We chose some machine learning models that can work with our data set,
and tested the accuracy to see which would work best:

![four](https://github.com/emilyt1985/emilyt1985.github.io/blob/master/images/3.png)


We then did further testing with hard and soft voting classifiers:

![five](https://github.com/emilyt1985/emilyt1985.github.io/blob/master/images/5.png)


Since no one model was the best predictor for all the justices, we decided to test the linear SVM on all of them.

![six](https://github.com/emilyt1985/emilyt1985.github.io/blob/master/images/6.png)


This is how our model tested against the data.
We also used a confusion matrix to compare the number of true and false negatives and positives to the data.

![seven](https://github.com/emilyt1985/emilyt1985.github.io/blob/master/images/7.png)


Lastly, we saved the model:

![eight](https://github.com/emilyt1985/emilyt1985.github.io/blob/master/images/8.png)

