## Transfer learning from quickdraw to MNIST

A thought experiment. Does transfer learning work for a network trained on images made up of doodles?
To recap, the CNN trained on quickdraw was 6 layers deep, with ~2M parameters, achieving 78% top-1 accuracy for the quickdraw dataset.

The expectation is that we should expect the transfer learnt model to do pretty well especially for low training samples, and not too great with large training samples (since the model trained from scratch can learn features directly).

## Findings

Starting with the MNIST fashion dataset, I extracted the logit layer from the CNN, and pumped the features to a SVM with linear kernel. 

Surprisingly, the SVM trained on the quickdraw embeddings did not fair that well. e.g. At 30 samples, (~3 per class), the network only got 49% accuracy, as compared to 61% when the SVM was trained directly on the raw pixels.

Perhaps a slight lesson learnt is to be mindful of the dataset of the pretrained embeddings. In this case, the doodles from quickdraw were clearly not good proxies for the fashion dataset.