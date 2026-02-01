Neural networks — learning notes

Went through ~37 mins of the Welch Labs – Neural Networks Demystified playlist on YouTube (free). Writing these down so things stick.

Regression vs classification was the starting point. Regression deals with continuous outputs, while classification is about assigning categories.

Artificial Neural Networks are loosely inspired by how neurons in the brain work — basically a mathematical representation. You have input and output layers, and the layers in between are hidden layers. When there are many hidden layers, it becomes deep learning.

Hyperparameters define how the network behaves. You don’t learn them — you choose them to fix the structure of the model.

Then came forward propagation. This can be implemented using MATLAB or NumPy. Inputs (x) and weights (w) are combined to compute z, which is passed through an activation function like sigmoid. The output gives initial estimates, which are usually off because the network isn’t trained yet.

Training means minimizing the cost function. One way to do that is by updating the weights, which is where gradient descent comes in.

Brute force approaches don’t work because of the curse of dimensionality. The number of combinations grows so fast that it would take longer than the age of the universe to compute.

Backpropagation solves this by efficiently computing gradients using partial derivatives and the chain rule. This is where calculus becomes essential.

Quick refresher: slope is rise over run. If y = x², then y′ = 2x. Understanding derivatives from first principles (using limits) helps later with numerical gradient checking.

Finally, training pitfalls. Poor training can lead to overfitting — performing well on training data but badly on unseen data. Regularization helps control model complexity and improves generalization.