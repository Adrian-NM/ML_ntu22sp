Optimized the original DNN to pass the strong baseline.

Model:
1. Add hidden layers.
2. Use BatchNor1d() and Dropout() to speed up training and avoid overfitting.
3. Use LearkyRuLU() to avoid gradient vanishing.

Feature Selection:
1. Use SelectKBest from sklearn library to select 24 most important features.

Traning Loop:
1. Use Adam optimizer to penalize large parameters thus avoid overfitting.
2. Use CosineAnnealing to avoid local minima.
