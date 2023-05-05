Download Link: https://assignmentchef.com/product/solved-dsci552-homework-5
<br>
<h1>1.    Multi-class and Multi-Label Classification Using Support Vector Machines</h1>

<ul>

 <li>Download the Anuran Calls (MFCCs) Data Set from: https://archive.ics. uci.edu/ml/datasets/Anuran+Calls+%28MFCCs%29. Choose 70% of the data randomly as the training set.</li>

 <li>Each instance has three labels: Families, Genus, and Species. Each of the labels has multiple classes. We wish to solve a multi-class and multi-label problem. One of the most important approaches to multi-label classification is to train a classifier for each label (binary relevance). We first try this approach:

  <ol>

   <li>Research exact match and hamming score/ loss methods for evaluating multilabel classification and use them in evaluating the classifiers in this problem.</li>

   <li>Train a SVM for each of the labels, using Gaussian kernels and one versus all classifiers. Determine the weight of the SVM penalty and the width of the Gaussian Kernel using 10 fold cross validation.<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a> You are welcome to try to solve the problem with both standardized <a href="#_ftn2" name="_ftnref2"><sup>[2]</sup></a> and raw attributes and report the results.</li>

  </ol></li>

</ul>

<ul>

 <li>Repeat 1(b)ii with <em>L</em><sub>1</sub>-penalized SVMs.<a href="#_ftn3" name="_ftnref3"><sup>[3]</sup></a> Remember to standardize<sup>4 </sup>the attributes. Determine the weight of the SVM penalty using 10 fold cross validation.</li>

</ul>

<ol>

 <li>Repeat 1(b)iii by using SMOTE or any other method you know to remedy class imbalance. Report your conclusions about the classifiers you trained.</li>

 <li>Extra Practice: Study the Classifier Chain method and apply it to the above problem.</li>

 <li>Extra Practice: Research how confusion matrices, precision, recall, ROC, and AUC are defined for multi-label classification and compute them for the classifiers you trained in above.</li>

</ol>

<ol start="2">

 <li><strong>K-Means Clustering on a Multi-Class and Multi-Label Data Set</strong></li>

</ol>

<strong>Monte-Carlo Simulation: </strong>Perform the following procedures 50 times, and report the average and standard deviation of the 50 Hamming Distances that you calculate

<ul>

 <li>Use k-means clustering on the whole Anuran Calls (MFCCs) Data Set (do not split the data into train and test, as we are not performing supervised learning in this exercise). Choose <em>k </em>∈{1<em>,</em>2<em>,…,</em>50} automatically based on one of the methods provided in the slides (CH or Gap Statistics or scree plots or Silhouettes) or any other method you know.</li>

 <li>In each cluster, determine which family is the majority by reading the true labels. Repeat for genus and species.</li>

 <li>Now for each cluster you have a majority label triplet (family, genus, species). Calculate the average Hamming distance, Hamming score, and Hamming loss<a href="#_ftn4" name="_ftnref4"><sup>[4]</sup></a>between the true labels and the labels assigned by clusters.</li>

</ul>

<ol start="3">

 <li>ISLR 12.7.2</li>

 <li>Extra Practice: The rest of problems in 12.7.</li>

</ol>

<a href="#_ftnref1" name="_ftn1">[1]</a> How to choose parameter ranges for SVMs? One can use wide ranges for the parameters and a fine grid (e.g. 1000 points) for cross validation; however,this method may be computationally expensive. An alternative way is to train the SVM with very large and very small parameters on the whole training data and find very large and very small parameters for which the training accuracy is not below a threshold (e.g., 70%). Then one can select a fixed number of parameters (e.g., 20) between those points for cross validation. For the penalty parameter, usually one has to consider increments in log(<em>λ</em>). For example, if one found that the accuracy of a support vector machine will not be below 70% for <em>λ </em>= 10<sup>−3 </sup>and <em>λ </em>= 10<sup>6</sup>, one has to choose log(<em>λ</em>) ∈ {−3<em>,</em>−2<em>,…,</em>4<em>,</em>5<em>,</em>6}. For the Gaussian Kernel parameter, one usually chooses linear increments, e.g. <em>σ </em>∈ {<em>.</em>1<em>,.</em>2<em>,…,</em>2}. When both <em>σ </em>and <em>λ </em>are to be chosen using cross-validation, combinations of very small and very large <em>λ</em>’s and <em>σ</em>’s that keep the accuracy above a threshold (e.g.70%) can be used to determine the ranges for <em>σ </em>and <em>λ</em>. Please note that these are very rough rules of thumb, not general procedures.

<a href="#_ftnref2" name="_ftn2">[2]</a> It seems that the data are already normalized.

<a href="#_ftnref3" name="_ftn3">[3]</a> The convention is to use <em>L</em><sub>1 </sub>penalty with linear kernel. <sup>4</sup>It seems that the data are already normalized.

<a href="#_ftnref4" name="_ftn4">[4]</a> Research what these scores are. For example, see the paper A Literature Survey on Algorithms for Multi-label Learning, by Mohammad Sorower.