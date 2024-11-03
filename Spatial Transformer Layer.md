CNN is unable to address scaling and rotation,
so we use STL to transform the original picture.

![[Pasted image 20241103152115.png|400]]
1. Input Image: receive the original feature map 
2. Parameter Prediction (Localisation net)
	- predict the 6 parameters for transformation
3. Coordinate Mapping (Grid generator)
	- use the predicted parameters to describe **the affine transfomation from the target to the origianl feature map**
	- Expansion, Compression, Translation, Rotation
		Somewhat like [[3. 齐次变换矩阵|Homogeneous transformation matrix]] in Kinamatics, but 2D version
		![[2024-11-03 13-54-56 的屏幕截图.png|400]]
4. Interpolation (Sampler)
	Problem 1: after Coordinate Mapping, new pixels' coordinate may not be integers, thus couldn't find an exact position
	Solution: use **Nearest-Neighbor Interpolation** to fill every pixels in the transformed picture with the RGB value of the nearset point
	Problem 2: Nearest-Neighbor Interpolation is not differentiable, thus cannot use GD
	Solution: use **Bilinear Interpolation** 
	![[2024-11-03 14-54-08 的屏幕截图.png|400]]
