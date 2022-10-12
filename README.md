# STL-10 dataset

The STL-10 dataset is an image recognition dataset for developing unsupervised feature learning, deep learning, self-taught learning algorithms. It is inspired by the [CIFAR-10](http://www.cs.toronto.edu/~kriz/cifar.html) dataset but with some modifications. In particular, each class has fewer labeled training examples than in CIFAR-10, but a very large set of unlabeled examples is provided to learn image models prior to supervised training. The primary challenge is to make use of the unlabeled data (which comes from a similar but different distribution from the labeled data) to build a useful prior. We also expect that the higher resolution of this dataset (96x96) will make it a challenging benchmark for developing more scalable unsupervised learning methods.

## Overview
- 10 classes: airplane, bird, car, cat, deer, dog, horse, monkey, ship, truck.
- Images are 96x96 pixels, color.
- 500 training images (10 pre-defined folds), 800 test images per class.
- 100000 unlabeled images for unsupervised learning. These examples are extracted from a similar but broader distribution of images. For instance, it contains other types of animals (bears, rabbits, etc.) and vehicles (trains, buses, etc.) in addition to the ones in the labeled set.
- Images were acquired from labeled examples on [ImageNet](http://www.image-net.org/).

## Testing Protocol
We recommend the following standardized testing protocol for reporting results: 
- Perform unsupervised training on the unlabeled.
- Perform supervised training on the labeled data using 10 (pre-defined) folds of 100 examples from the training data. The indices of the examples to be used for each fold are provided.
- Report average accuracy on the full test set.

## Utils
After battling for some time with reading the STL-10 dataset from the raw binary files in python 2.7, I've managed to load them quite easily and I'm sharing the solution here in hopes of saving time for other people.

The usage is relatively straightforward, the file `stl10_input.py` contains all the necessary methods for downloading and reading data along with a test main funct for displaying an image.

## Reference
* Please cite the following reference in papers using this dataset:

Adam Coates, Honglak Lee, Andrew Y. Ng An Analysis of Single Layer Networks in Unsupervised Feature Learning AISTATS, 2011. ([PDF](http://cs.stanford.edu/~acoates/papers/coatesleeng_aistats_2011.pdf))
* Please use http://cs.stanford.edu/~acoates/stl10 as the URL for this site when necessary.

## Contact
Send questions to Adam Coates: acoates@cs.stanford.edu
