# Additions with Neural Nets

We train a neural network to 'add' two integers by performing classification. i.e. Given 2 input integers of range [0, m], give a output of 2m classes.

## Results
After removing 3 numbers from the training set, and ~50K samples, can attain 96.7% on test set (which consist of *ONLY* samples containing the removed numbers)

## Possible improvements
1. Try balancing the outputs samples (so that each output class can be trained appropriately)