# EECS 738 - Says One Neuron To Another
The purpose of this project is to understand how neural networks function and how underlying mathematics work by coding it from scratch

### *Data*
Following datasets are used in the project:
- [Bank_marketing_dataset](./data/bank.csv)
- [Mushrooms](./data/mushrooms.csv)

This datasets are retireved from 'https://en.wikipedia.org/wiki/List_of_datasets_for_machine-learning_research'


#### Bank Marketing Datset
This dataset looks at different features such as **Age**, **Job**, **Housing**, **Loan**, **Emp.var.rate** and determines whether client has subscribed to a term **deposit**.

#### Mushroom Dataset
The mushroom classification dataset looks at different features of both poisonous (p) and edible (e) mushrooms

Some interesting features include:
* cap shape
* cap surface
* bruises
* odor
* ring number
* ring type
* gill color

### **Process - Neural Network Implementation**

Neural nework can be thought as an mathematical function that maps given input to desired output and it mainly consists of 
* Input Layer
* Arbitrary amount of hidden layers
* Output Layer
* Set of weights and biases between each layer, **W** and **b**
* Activation functions


#### Input Layers
The width of the input layer was chosen to match the number of features for each dataset. For the Bank  dataset, the input layer was given a width of 20, since it has 20 features. The mushroom dataset has 22 features, so the input layer width is of size 22.
#### Hidden Layers
For both datsets, the hidden layer width was arbitrarily set to size 20.
#### Output Layers
Both datasets are looking to solve classification problems. Therefore, the width of the output layer was set to match the number of possible classes for a given observation. For the Bank dataset, the output layer width was set to size 1, since its network is attempting to correctly classify an animal to its given class (yes, no). Similarly for the mushroom dataset, the output layer width was set to size 1, since the network is trying to predict whether a given mushroom is edible (e) or poisonous (p).
#### Activation functions
For both networks, the rectified linear unit (ReLU) was chosen as the activation functions for the hidden layer. ReLUs perform fast calculations and are known to avoid the vanish gradient problem that occurs with logistic sigmoid activation functions.

The activation functions for the output layers are same as well since the neural networks are trying to solve binary classification in each case.  For both the datatsets, the logistic sigmoid activation function was chosen for the output layer. This is because sigmoid functions output an integer between 0 and 1, which is useful for binary classification problems.
#### **Training and Testing**
75% of the data was used to train the model, while the other 25% was used for testing. Both models were then trained for a length of 10000 epochs.

### **Discussion**
The neural network model for the Bank dataset had an accuracy of 79%. This model  finished training much faster than the model used for the mushroom dataset because the computations for the derivative of the ReLU activation function are much quicker than those for the derivative of the sigmoid activation function.

The neural network model for the mushroom dataset had an accuracy of about 69%. However, it also had a precision score of 74%. This means that the network only predicted that almost all mushrooms would be poisonous. Since 69% of the test data samples were poisonous mushrooms, the network achieved an accuracy of 74%. However, if the distribution of the test data was different, then the accuracy of the neural network would have significantly changed.

### References

https://towardsdatascience.com/how-to-build-your-own-neural-network-from-scratch-in-python-68998a08e4f6

https://www.analyticsvidhya.com/blog/2020/07/neural-networks-from-scratch-in-python-and-r/?#

https://ml-cheatsheet.readthedocs.io/en/latest/backpropagation.html
