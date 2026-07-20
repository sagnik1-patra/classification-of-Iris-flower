# Assignment 1 Report: ANN Fundamentals Using NumPy

## 1. Objective

The objective was to implement a multi-layer perceptron from scratch using
NumPy and classify the three Iris species: setosa, versicolor, virginica.
The implementation includes parameter initialization, forward propagation,
cross-entropy loss, backpropagation, mini-batch gradient descent, prediction,
evaluation, and early stopping.

## 2. Data Preparation

The Iris dataset contains 150 observations and four numerical input features.
A stratified split was used to create 70% training data, 15% validation data,
and 15% test data. Z-score normalization was fitted only on the training set
and then applied to validation and test data. Labels were converted into
three-element one-hot vectors.

The generated exploratory outputs include feature histograms, a pair plot,
and a feature-correlation heatmap. Petal length and petal width show a strong
positive relationship and provide substantial class-separation information.

## 3. Network Architecture

The required baseline architecture was used:

- Input layer: 4 neurons
- Hidden layer 1: 8 sigmoid neurons
- Hidden layer 2: 6 sigmoid neurons
- Output layer: 3 softmax neurons

Weights were initialized using scaled random values. Hidden layers used the
selected activation function, while the output layer used softmax to obtain
class probabilities.

## 4. Forward Propagation and Loss

For each layer, the linear output was calculated as:

`Z = A_previous × W + b`

The hidden activation was then applied to produce the next activation.
The final layer used softmax. Categorical cross-entropy measured the error
between predicted probabilities and one-hot encoded labels.

## 5. Backpropagation

The output-layer gradient simplifies to predicted probabilities minus the
one-hot target when softmax is combined with cross-entropy. Gradients were
propagated backward through the network using the chain rule. Weight gradients
were calculated from the previous layer's activations and the current layer's
error term. Parameters were updated with mini-batch gradient descent.

## 6. Baseline Results

The custom NumPy network achieved a test accuracy of
**0.6957**. Precision, recall, and F1-score for each class are
available in `classification_report.csv` and `classification_report.txt`.
The confusion-matrix heatmap shows the distribution of correct and incorrect
predictions.

## 7. Hyperparameter Experiments

### Learning Rate

- Learning rate 0.001: test accuracy 0.3043, final loss 1.0930.
- Learning rate 0.01: test accuracy 0.6957, final loss 0.4088.
- Learning rate 0.1: test accuracy 1.0000, final loss 0.0425.

A very small learning rate generally changes parameters slowly and may need
more epochs. A larger learning rate converges faster but can become unstable
if updates overshoot useful parameter values.

### Activation Function

The strongest activation in this run was **relu**. Sigmoid is
smooth but may produce small gradients in deeper networks. Tanh is zero-centered
and often trains faster on standardized data. ReLU avoids saturation for
positive inputs but can produce inactive neurons when many pre-activations are
negative.

### Network Depth

- Shallow 4-8-3: test accuracy 0.9565.
- Required 4-8-6-3: test accuracy 0.8696.
- Deeper 4-12-8-6-3: test accuracy 0.8696.

The strongest tested architecture was **4-8-3**. Additional
depth increases model capacity, but Iris is a small dataset, so an unnecessarily
deep network can overfit or become harder to optimize.

### Batch Size

A mini-batch size of 16 was used. It provides more stable gradients than
single-sample updates while still introducing enough variation to help
optimization. Very large batches would make updates smoother but reduce the
number of updates per epoch.

## 8. Comparison with sklearn

The NumPy model achieved 0.6957 test accuracy, while sklearn's
MLPClassifier achieved 0.6522. Small differences are expected
because sklearn includes its own convergence rules and optimized numerical
implementation. The comparison confirms whether the manually implemented
forward and backward calculations behave reasonably.

## 9. Best Configuration

The highest test accuracy in the experiment table was
**1.0000**, produced by:

- Configuration: LR 0.1
- Architecture: 4-8-6-3
- Activation: sigmoid
- Learning rate: 0.1

## 10. Conclusion

The assignment demonstrates that a complete neural network can be built using
basic NumPy matrix operations. Standardization, suitable initialization,
activation choice, learning rate, and network depth all influence convergence.
For Iris, a modest architecture is sufficient because the dataset is small and
the classes are reasonably separable, especially through petal measurements.
