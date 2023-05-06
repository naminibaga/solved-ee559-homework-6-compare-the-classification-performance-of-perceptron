Download Link: https://assignmentchef.com/product/solved-ee559-homework-6-compare-the-classification-performance-of-perceptron
<br>
<ol>

 <li>In this problem, you are asked to compare the classification performance of perceptron (sequential gradient descent or similar version) and MSE (pseudoinverse version) classifiers on the wine dataset. This problem is designed to be used with the functions provided by the PRTools5 toolbox (if using Matlab), or the named functions from scikit-learn (if using Python).</li>

</ol>

For this problem, use the wine dataset files provided in the HW1 folder.

<ul>

 <li>State clearly whether you are using PRTools5 and Matlab, or scikit-learn and Python.</li>

 <li>Store a copy of the unnormalized data (as provided), and also a standardized version of the data, for your use. Standardized means each feature is normalized to 0 mean and unit variance.  Note that the normalizing factors should be calculated from the training data only (why?), and then applied to both the training data and test data.</li>

</ul>

For this part, report on the mean and standard deviation of each feature of the unnormalized training data, and answer the “why?” question above.

<strong>Hint:</strong>  For part (b), you may either code it yourself, or use available functions: scikitlearn’s function sklearn.preprocessing.StandardScaler, or Matlab’s function zscore().  If you use these functions, then be sure you know the formulas to apply standardization so you understand the algebra as well.

<em> </em>

<em>         Parts (c)-(f) below use perceptron.  For these parts, use standardized data.  </em><em>   </em>

<ul>

 <li>For the perceptron classifier (perlc in PRTools5 or sklearn.linear_model.Perceptron in Python), answer the following questions (by looking at the documentation, comments, or the code, as needed):

  <ul>

   <li>What is the default initial weight vector?</li>

   <li>What is the halting condition? If the solution weight vector (which would correctly classify all training data points) is not reached, what is the backup halting condition?</li>

  </ul></li>

</ul>

<strong>Hints for (ii):</strong>  (1) For both PRTools and scikit-learn, this may require some digging into the code to answer.  Note that for PRTools, the backup halting condition is not just the runtime.  (2) If you prefer, you can skip this for now and answer most of the parts below without the answer to (c)(ii); then come back to finish this.

<ul>

 <li>This part will be done twice: once using only the first 2 features, and then again using all 13 features.</li>

</ul>

Apply the perceptron learning algorithm to the training data, using the one vs. rest method.  Report the resulting 3 weight vectors and the classification accuracy of your classifier on both the training set and the test set.

<strong>Tips:</strong>

PRTools5 users:  Note that perlc first augments and standardizes the data by default, so you can input the unnormalized unaugmented data.  Also, one vs. rest is the default method.  testc will give classification error rate.  You can retrieve weight vectors using getWeightsFromPrmapping.m (provided in the HW7 folder).

Scikit-learn users:  You can extract the weight vectors using model.coef (for nonaugmented <em><sub> </sub></em><em><u>w </u></em>) and model.intercept (for <em><sub> </sub>w</em><sub>0</sub>).

<ul>

 <li>This part should also be done twice (for the first 2 features and for all 13 features). Run the perceptron of part (d) 100 times, with randomly chosen starting weight vectors each time.  Pick the run that has the best performance on the training set.  (If there is a tie for the best performing run, pick one of the runs at random.)  Report the final 3 weight vectors, and the classification accuracy on both the training set and the test set.</li>

 <li>Compare and comment on your results from (d) and (e) on training data and on test data. That is, compare 2 features to 13 features in (d) for each dataset; likewise compare 2 features to 13 features for in (e) for each dataset.  Also, compare (d) to (e) for 2 features for each dataset; and compare (d) to (e) for 13 features for each dataset.</li>

</ul>




<em>        Parts (g)-(j) below use MSE (pseudo-inverse version) classification.  Please also refer to the tips for PRTools implementation and for scikit-learn implementation below (on next page).   </em>

<ul>

 <li>For this part use unnormalized data. Run the pseudoinverse classifier, and report the classification accuracy on the test data, for the first 2 features and for all 13 features.</li>

 <li>Repeat part (g) except using standardized data.</li>

 <li>Compare your test-accuracy results of (g) and (h). Are they identical, similar, or quite different?</li>

 <li>Compare and comment on your test-accuracy results of (h) and (e). Are they identical, similar, or quite different?</li>

</ul>




<em>            Tip for PRTools5 implementation of pseudoinverse classifier </em>            Use fisherc.




<em>         Tips for scikit-learn implementation of pseudoinverse classifier </em>

Use sklearn.linear_model.LinearRegression.  This regression function can be used for 2class classification.

&gt;      Use non-reflected data points.

&gt;      Refer to Discussion 7 and related document posted on D2L for more tips.




<ol start="2">

 <li>Note: in this problem you may do the plots by hand or by computer (your choice); but everything else (e.g., the quadratic mapping, finding decision regions and boundaries, etc.) is to be done by hand.</li>

</ol>

In a 2-class problem with 2 features, you are given the following training data:




<h1><em>S</em><sub>1</sub>: (0,0)<em>T </em>, (0,1)<em>T </em>, (0,−1)<em><sup>T   </sup></em> <em>S</em>2 : (−2,0)<em>T </em>, (−1,0)<em>T </em>, (0,2)<em>T </em>, (0,− 2)<em>T </em>, (1,0)<em>T </em>, (2,0)<em>T</em></h1>

<em> </em>




<ul>

 <li>Plot the points in 2D (non-augmented) feature space. Are they linearly separable?</li>

</ul>

The rest of this problem deals with using a phi-machine approach to get a nonlinear classifier.  Use a quadratic polynomial mapping, and order the components of your mapped vectors <em><sub> </sub><u>u</u></em> the same as we did in lecture.

<ul>

 <li>List the points [as (<em>D</em>′ +1)-tuples] in expanded feature space.</li>

</ul>

<em> </em>

<ul>

 <li>Find a decision boundary (by hand) in the expanded feature space. [<strong>Hint</strong>: try plotting</li>

</ul>

the points in (<em>x</em><sub>1</sub><sup>2</sup>,<em>x</em><sub>2</sub><sup>2</sup>) space.]  Plot the boundary and decision regions (in <em><sub> </sub></em>(<em>x</em><sub>1</sub><sup>2</sup>,<em>x</em><sub>2</sub><sup>2</sup>)

<em><sub> </sub></em>

space), and give a complete weight vector <em><sub> </sub><u>w</u></em>′ that correctly separates the prototypes in the expanded feature space.  Also state the decision rules in the notation of the expanded feature space (i.e., in terms of the <em>u</em><em><sub>i</sub></em> ).

<ul>

 <li>Map the decision boundary and rules/regions that you found in (c) back into the original feature space: that is, give the decision rules in this space (in terms of <em>x</em>1and <em>x</em>2 ), and give an equation for the decision boundary (in terms of <em> x</em>1and <em>x</em>2 ).</li>

</ul>

<em> </em>

Plot the data points, decision boundary, and show the decision regions, all in the original ( <em>x</em><sub>1</sub>,<em>x</em><sub>2</sub>) feature space.


