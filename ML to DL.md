Simple linear model cannot be piecewise or curved, so there is Model Bias
New model use more features and new structure, therefore eliminate the model bias
![[2024-10-20 14-02-39 的屏幕截图.png|400]]
How the parameters effect the model ![[2024-10-20 13-57-04 的屏幕截图.png|400]]
The model can be written in matrix multiplication
![[2024-10-20 14-08-22 的屏幕截图.png|400]]
- x: features
- other parameters are unkown, set randomly, **but can be optimized**
#### Optimization
Put all unkown parameters ($w_{ij}, b_i, c_i, b$) into a column, $\theta$
How do we measure the parameters are good or not?
-- By **Loss function** $L(\theta)$
To find the $\theta$ that minimize $L(\theta)$, we can use Gradient Descent

GD *vs* BGD: BGD speeds up the optimization
**NOTE: 1 epoch = see all the batches once**

#### Activation Function
Remember that Sigmoid was used to introduce non-linearity into the model.
In fact, there are other functions that have the same effect, called **Activation Function**
- Sigmoid 
- ReLU 
- ...
#### More Layers
After applying the Activation function, the output can be seen as new features, thus our model would be complex.
![[2024-10-20 14-48-03 的屏幕截图.png|400]]
**Deep** Learning: "deep" indicates many hidden layers
 
#### Hyperparameters
- Learning rate
- Batch size
- number of neurons per layer (number of activation functions)
- type of activation function
- number of layers
- ...