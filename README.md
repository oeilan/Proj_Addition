# Proj_Addition

Simple dense layer neural net to compute addition of 2 numbers x1, x2 between 0 and 100 and output answer in one-hot vector, Y

The problem boils down to using a dense layer neural net to convert a single integer into a one-hot vector. Theoretically, there is a explicit solution to this:

Let Z1 be the integer which ranges between 0 and 199 which has to be converted into one-hot Let Z2 be a vector derived by multiplying Z1 by [1/0.0001, 1/1, 1/2, 1/3, 1/4 ... 1/198] and following by subtracting 1 from result. Apply activation function -Abs(Z2) to obtain a vector where maximum value is found at the corresponding positon with 1 value of the one-hot vector. Set maximum value to 1 and rest zero.

Attempt was made to build model with 2 hidden layers and input layer of 2 nodes: (1) first hidden layer comprises of one node, holding the sum of x1 and x2 (Z1) (2) second 199-node hidden layer computes Z2 and custom activation of Z2 described above (3) 199-node output layer uses sigmoid or softmax activation

However, model was unable to converge without performing kernal initialization.

Alternative model of single 200-node dense hidden layer with 2 concatenated one-hot vectors as input was built. This model was able to attain 100% train accuracy but only around 59% test accuracy with train data being 80% random samples from universe of all possible inputs and test being the remaining 20%.
