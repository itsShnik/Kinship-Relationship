# Kinship Relationship Prediction
Prediction of Kinship relationship between people given the pair of images

The dataset used in this repository is taken from this [kaggle challenge](https://www.kaggle.com/c/recognizing-faces-in-the-wild/overview)

# Problem Statement
Build a model to determine if two people are blood-related based solely on images of their faces.

# Format of the Dataset
The dataset is a subset of the Face in the Wild dataset which contains multiple images of each person in a family. A csv file contains the information if two different persons are blood-related (i.e, share kinship relationship).

# Approach
To approach the solution of this problem _Siamese Networks_ are used. Siamese neural networks are basically networks which map two or more different input to output vectors using same function say _&alpha;_. The two or more output vectors are then combined using some other function _&beta;_ to get a set of _Siamese_ features. A commonly used function _&beta;_ is the L2 distance between the vectors obtained. Now, a single layered perceptron can be used on top of these features to classify whatever property is needed to.

Siamese networks are specially found useful for the tasks which require calculating the similarity between two objects. Hereby, we use the concatenation of the L2 distance between the vectors obtained from the function _&alpha;_ with the vectors themselves.

Resnet50 with weights pretrained on VGG_Face dataset when trained end to end seems to give optimal results. Hyperparameter tuning can help improve the results significantly.
