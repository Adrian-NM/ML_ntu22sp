Optimized the model to near strong baseline.
Private: 0.72646
Public: 0.74487

1. Add concat_nframes to learn from the context.
2. Add hidden_layers and hidden_dim.
3. Add batch_size to speed up the training.
4. Add BatchNorm and Dropout in the hidden layers.
5. Use LeakyReLU to avoid gradient vanishing.
6. Add CosineAnnealingWarmRestarts.
7. Use weight_decay in Adam optimizer.
8. Add early_stopping to save time.