+ binary: binary cross-entropy & sigmoid
	+ binary cross-entropy: $\frac{1}{N} \sum_{i=1}^N \left[ y_i \log(p_i) + (1-y_i) \log(1-p_i) \right]$
	+ sigmoid: $\frac{1}{1+e^{-t}}$
+ multiclass: cross-entropy & softmax
	+ categorical cross-entropy (ha one-hot encoded): $- \sum_i^C y_i \log(p_i)$
	+ softmax: $\frac{e^{z_i}}{\sum_{j=1}^K e^{z_j}}$ (lényegében mindent e-adra emel, majd lenormalizálja)
+ regression: MAE **MSE** MAPE & linear (ReLU ha nemnegatív)
	+ MSE: $\frac{1}{N} \sum_{i=1}^N (y_i - p_i)^2$