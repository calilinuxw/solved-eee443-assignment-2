Download Link: https://assignmentchef.com/product/solved-eee443-assignment-2
<br>
An engineer is trying to design a linear neural network for a regression task. The design is based on the following cost function:

<strong> w<sup>T</sup>x</strong><em><sup>n</sup></em>)<sup>2                                                                                                         </sup>(1)

where <em>y<sup>n </sup></em>is scalar output and <strong>x<sup>n </sup></strong>is the vector input for the <em>n<sup>th </sup></em>training/testing sample. Answer the questions below.

<ol>

 <li>Prove that minimizing <em>C</em><sub>1 </sub>is equivalent to minimizing another cost of the following form:</li>

</ol>

<strong>w<sup>T</sup>Aw </strong>− <strong>b<sup>T</sup>w                                                        </strong>(2)

Find the expressions for <strong>A </strong>and <strong>b </strong>in terms of the input and output of the network. Find the update rule for ∆<strong>w </strong>according to gradient descent optimization.

<ol>

 <li>Identify an appropriate change of variables to prove that the update rule obtained in <strong>part a </strong>is equivalent to the update rule for a different cost function:</li>

</ol>

<strong>w˜<sup>T</sup>Aw˜                                                             </strong>(3)

Express <strong>w˜ </strong>in terms of <strong>w</strong>, <strong>A </strong>and <strong>b</strong>.

<ol>

 <li>Assume that <strong>A </strong>is a symmetric and positive-definite matrix. Find the maximum learning rate <em>η </em>for which the weight updates lead to a stable solution.</li>

</ol>

<h1>Question 2.</h1>

In this question we will revisit the cat versus car detection problem from the previous assignment. The file assign2_data1.mat contains the variables trainims (training images) and testims (testing images) along with the ground truth labels trainlbls and testlbls. You will implement stochastic gradient descent on mini-batches.

Here, you will measure the error term as a function of epoch number, where an epoch is a single pass through all images in the training set. Two different error metrics will be calculated: the mean squared error and the mean classification error (percentage of correctly classfied images). Record the error metrics for each epoch separately for the training samples and the testing samples. Answer the questions below.

<ol>

 <li>Using the backpropagation algorithm, design a multi-layer neural network with a single hidden layer. Assume a hyperbolic tangent activation function for all neurons. Experiment with different number of neurons <em>N </em>in the hidden layer, initialization of weight and bias terms, and mini-batch sample sizes. Assuming a learning rate of <em>η </em>∈ [0<em>.</em>1 0<em>.</em>5], select a particular set of parameters that work well. Using the selected parameters, run backpropagation until convergence. Plot the learning curves as a function of epoch number for training squared error, testing squared error, training classification error, and testing classsification error.</li>

 <li>Describe how the squared-error and classification error metrics evolve over epochs for the training versus the testing sets? Is squared error an adequate predictor of classification error?</li>

 <li>Train separate neural networks using substantially smaller and larger number of hiddenlayer neurons (<em>N<sub>low </sub></em>and <em>N<sub>high</sub></em>). Plot the learning curves for all error metrics, overlaying the results for <em>N<sub>low</sub></em>, <em>N<sub>high </sub></em>and <em>N</em><sup>∗ </sup>prescribed in <strong>part a</strong>.</li>

 <li>Design and train a separate network with two hidden layers. Assuming a learning rate of <em>η </em>∈ [0<em>.</em>1 0<em>.</em>5], select a particular set of parameters that work well. Plot the learning curves for all error metrics, and comparatively discuss the convergence behavior and classification performance of the two hidden-layer network with respect to the network in <strong>part a</strong>.</li>

 <li>Assuming a momentum coefficient of <em>α </em>∈ [0<em>.</em>1 0<em>.</em>5], retrain the neural network described in <strong>part d</strong>. Select a particular set of parameters that work well. Plot the learning curves for all error metrics, and comparatively discuss the convergence behavior with respect to <strong>part d</strong>.</li>

</ol>

<h1>Question 3.</h1>

Neural network architectures can produce powerful computational models for natural language processing. Here, you will consider one particular model for examining sequences of words. The task is to predict the fourth word in sequence given the preceding trigram, e.g., trigram: ‘Neural nets are’, fourth word: ‘awesome’. A database of articles were parsed to store sample fourgrams restricted to a vocabulary size of 250 words. The file assign2_data2.mat contains training samples for input and output (trainx, traind), for validation (valx, vald), and for testing (testx, testd). Using these samples, the following network should be trained via backpropagation:

units

The input layer has 3 neurons corresponding to the trigram entries. An embedding matrix R (250×D) is used to linearly map each single word onto a vector representation of length D. The same embedding matrix is used for each input word in the trigram, without considering the sequence order. The hidden layer uses a sigmoidal activation function on each of P hidden-layer neurons. The output layer predicts a separate response <em>z<sub>i </sub></em>for each of 250 vocabulary words, and the probability of each word is estimated via a soft-max operation <strong>a) </strong>Assume the following parameters: a stochastic gradient descent algorithm, a mini-batch size of 200 samples, a learning rate of <em>η </em>= 0<em>.</em>15, a momentum rate of <em>α </em>= 0<em>.</em>85, a maximum of 50 epochs, and weights and biases initialized as random Gaussian variables of std 0.01. If necessary, adjust these parameters to improve network performance. The algorithm should be stopped based on the cross-entropy error on the validation data. Experiment with different D and P values, (D,P) = (32,256), (16,128), (8,64) and discuss your results.

<ol>

 <li><strong>b) </strong>Pick some sample trigrams from the test data, and generate predictions for the fourth word via the trained neural network. Store the the predicted probability for each of the 250 words. For each of 5 sample trigrams, list the top 10 candidates for the fourth word. Are the network predictions sensible?</li>

</ol>