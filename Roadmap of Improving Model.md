![[Pasted image 20241029180451.png]]
After training, we may find that...
## Loss is large
The model doesnot perform well even in the traning set.
**Two possibilities: Model Bias or Optimization issues?**
#### Model Bias: the model is too simple
See the training process as finding a function in a function set. Model bias means that all functions in the function set cannot reduce the loss to the desired level. 
**Solution: redesign the model to make it more flexible**
- more features
- (in DL) more layers
#### Optimization
[*development of optimizers*](https://zhuanlan.zhihu.com/p/32230623)
The optimization approach cannot find the way to the lowest Loss 
1. **Case1 :critical point.** use *Second Partials Test* to confirm
	- local minima (very rare when the model is complex)
	- saddle point
	**Solutions to escape from the critical point**: 
	1. use [[梯度下降#批量梯度下降|Batch Gradient Descent]]
		*Small Batch v.s. Large Batch*![[Pasted image 20241029210436.png|400]]
	2. use Momentum (adjust the optimization direction with the last optimization)
		![[Pasted image 20241029211224.png|400]]
		$\lambda$ is the `momentum` hyperparameter
2. **Case2: skip over (the learning rate is so high)**
	**Solution: Adaptive Learning Rate**
	- Adagrad: use Root Mean Square of *all gradients in history* to update the learning rate.
		- if the RMS is big, decrease the learning rate
		- if the RMS is small, increase the learning rate
	- RMSProp: optimize Adagrad by adding a hyperparameter $\alpha$ which weights the current gradient's effect on learning rate
		*The most popular optimizer Adam = RMSProp + Momentum*
	- Learning Rate Scheduling
		- Learning Rate Decay
		- Warm Up (useful in training BERT)
			![[Pasted image 20241029224716.png|400]]
#### How to identify Model Bias / Optimization issue
Start from smaller / shallower networks, which are easier to optimize.
If **deeper networks do not obtain smaller loss on training data**, then there is optimization issue.
## Loss is small
Loss on traning data is small, which is good.
But when it turns to testing data, if the Loss is large, there are two possibilities: 
**Overfitting or Mismatch?**
#### Overfitting
Solution:
- More training data
	- data augmentation  e.g. flip the picture
- Constrain the model
	- Less parameters / neurons, sharing parameters(e.g. CNN's conv kernel)
	- Less features
	- Early stopping
	- Regularization
	- Dropout
#### Mismatch
The training data and testing data have different distributions
...
#### Bias-Complexity Trade-off
Low complexity --> Model Bias
High complexity -->Overfitting 
![[Pasted image 20241029183022.png|400]]
so it need to balance manually by **Cross Validation**:
Split the dataset into *training set* and *validation set*. The Loss on validation set measures the result.