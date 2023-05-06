Download Link: https://assignmentchef.com/product/solved-ece657a-data-and-knowledge-modeling-and-analysis-assignment-1
<br>
<strong>Assignment 1: </strong>Basic Environment Set-up and Classification

<h1>Overview</h1>

<strong>Collaboration: </strong>Do your work and report individually. You can collaborate on the right tools to use and setting up your programming environment.

<strong>Hand in: </strong>One report per person, via the CROWDMARK in PDF format. You will need to divide the PDF up into multiple 5 files and drag and drop ech onto the relevant question. You should receive an invite to crowdmark by email. But don’t worry if the division is not perfect, as long as each question’s answer is fully contained within that questions file. Also submit the code/scripts needed to reproduce your work as a python jupyter notebook to the LEARN dropbox. <strong>Specific objectives:</strong>

<ul>

 <li>Establish your software stack to carry out data analysis assignments for the rest of the course.</li>

 <li>Load datasets and perform some exploratory plots.</li>

 <li>Study how to apply some of the methods discussed in class and gain experience on the use of this classification methods (KNN, SVM, Decision Trees, Random Forest, Gradient Tree Boosting).</li>

</ul>

<strong>Tools: </strong>You can use libraries available in python. You need to mention which libraries you are using, any blogs or papers you used to figure out how to carry out your calculations.

<h1>Dataset</h1>

Use the Iris dataset from “sklearn.datasets.load iris”. This dataset is a classic and fairly simple benchmark for basic machine learning algorithms. It includes different features of three Iris flower species (setosa, versicolor, virginica).

<h1>Question 1</h1>

To begin understanding the dataset, plot the pairs plot (scatter plot matrix) of the data. Note that the pairs plot includes the scatter plots of every dimension versus another dimension.

After plotting, describe in words your interpretation of the separability of the three classes in terms of different features (dimensions).

<h1>Question 2: KNN</h1>

Classify the data using a KNN classifier. Tune the hyperparameters of the KNN classifier using sklearn functions. Plot the different validation accuracies against the values of the parameter and select the best hyperparameter to train the model. Report the resulting accuracy. Do the following details:

<ol>

 <li>First, divide the data into train, validation, and test sets (60%, 20%, 20%) <strong>*Note:* </strong>use random state=42 in the train test split function to get the same split every time you run the program.</li>

 <li>Train the model with each classifier’s default parameters. Use the trainset and test the model on the test set. Store the accuracy of the model.</li>

 <li>Then, you should find the best parameters of the classifiers, in this case,<em>k </em>for KNN. For this, use the validation set, NOT the test set. To find the best parameter you should:

  <ul>

   <li>Pick a value of parameter. Test the following values for validation: <em>k</em>: {1, 5, 10, 15, 20, 25, 30, 35}</li>

   <li>Train the model using the train set.</li>

   <li>Test the model with the validation set. Store the accuracy.</li>

   <li>When you finish trying all the possible parameters, plot a figurethat shows the relationship between the accuracy and the parameter. Report the best k in terms of classification accuracy.</li>

  </ul></li>

 <li>Now, using the best found parameters, train the model using the train setand test the model on the test set. Report the accuracy of the model.</li>

</ol>

<h1>Question 3: SVM</h1>

Classify data using a linear SVM classifier. Evaluate the best value for the term <em>C </em>amongst values:

<em>C</em>: [0.1, 0.5, 1, 2, 5, 10, 20, 50]

Here, rather than the procedures (2-4) as in Question 2, use 10-fold cross validation. First, randomly divide data into (80%, 20%) portions of train-validation and test sets (with random state=42). Then, apply 10-fold cross validation on the train-validation set. In every fold, 90% of data is used for training and 10% of data for validation. For every <em>C </em>value, a mean accuracy of the folds is found. The best mean accuracy determines the best value for C. Plot the mean accuracy versus the C values. Finally, report the test accuracy.

<h1>Question 4: Tree-based Classifiers</h1>

Classify the data using three tree-based classifiers: Decision Trees, Random Forests and Gradient Tree Boosting. Tune the hyper-parameters of the classifier using 10-fold cross validation and sklearn functions (as in Question 3). Evaluate the best value for the number of trees and maximum depth of trees.

For decision tree:

<ul>

 <li>max depth: {3, 5, 10, None (grow until the end)} For this, plot the mean accuracy versus the maximum depth.</li>

</ul>

For random forest:

<ul>

 <li>number of trees: {5, 10, 50, 150, 200}</li>

 <li>max depth: {3, 5, 10, None (grow until the end)}</li>

</ul>

For this, the plot should be a <strong>heat plot</strong>. You should have (5 * 4) mean accuracies for different values of number of trees and maximum depth.

For Gradient Tree Boosting (on sklearn it is GradientBoostingClassifier):

<ul>

 <li>number of estimators: {5, 10, 50, 150, 200}</li>

</ul>

For this, plot the mean accuracy versus the number of estimators.

<em>Note: the number of ‘trees’ grown by GBT is </em>n classes×n estimators <em>but this is handled automatically.</em>

Please leave the other parameters as default in sklearn.

<h1>Question 5: Analysis</h1>

<ol>

 <li>Explain why you had to split the dataset into train and test sets?</li>

 <li>Explain why when finding the best parameters for KNN you didn’t evaluate directly on the test set and had to use a validation test.</li>

 <li>What was the effect of changing <em>k </em>for KNN. Was the accuracy always affected the same way with an increase of <em>k</em>? Why do you think this happened?</li>

 <li>What was the relative effect of changing the max depths for decision treeand random forests? Explain the reason for this.</li>

 <li>Comment on the effect of the number of estimators for Gradient TreeBoosting and what was the relative effect performance of gradient boosting compared with random forest. Explain the reason for this.</li>

 <li>What does the parameter <em>C </em>define in the SVM classifier? What effect did you observe and why do you think this happened?</li>

</ol>

<h1>Notes</h1>

You might find the following links are useful to solve this assignment:

<ul>

 <li>https://scikit-learn.org/stable/modules/generated/sklearn.neighbors. KNeighborsClassifier.html</li>

 <li>https://scikit-learn.org/stable/modules/generated/sklearn.ensemble. RandomForestClassifier.html</li>

 <li>https://scikit-learn.org/stable/modules/generated/sklearn.svm. SVC.html</li>

 <li>https://scikit-learn.org/stable/modules/generated/sklearn.model</li>

</ul>

_selection.GridSearchCV.html

<ul>

 <li>https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.</li>

</ul>

GradientBoostingClassifier.html