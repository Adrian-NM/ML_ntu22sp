1. Data augumentation: randomly apply TrivialAugmentWide() with a probability of 0.95 in train_tfm.
2. Optimize the model structure: Use residual blocks to construct a deeper CNN.
3. Learning rate scheduler.
4. Merge the training and validation dataset to use K-fold Cross Validation.
5. Use FocalLoss for better performance in object detection. The alpha values are determined by the ratio of each label's number of samples.
