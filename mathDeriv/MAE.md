## Note: here we define it as |y_pred_i - y_true_i|  instead of   |y_true_i - y_pred_i|` 
### if we use |y_true_i - y_pred_i| , the derative will be -(1/N) * sign(y_true_i - y_pred_i)
### It doesn't matter just if we keep the consistency

To compute the derivative of the Mean Absolute Error (MAE) with respect to the predicted values, we need to differentiate the absolute value function inside the summation. First, let's rewrite the MAE formula for clarity:

`MAE = (1/N) * Σ|y_pred_i - y_true_i|`

Now, let's differentiate the absolute value function. Recall that the derivative of the absolute value function is the sign of its argument:

- `d(|x|)/dx = 1` if `x > 0`
- `d(|x|)/dx = -1` if `x < 0`
- `d(|x|)/dx` is undefined if `x = 0`

Let's denote the difference between the predicted value and the true target value as `d_i`:

`d_i = y_pred_i - y_true_i`

Now, we can rewrite the MAE formula as:

`MAE = (1/N) * Σ|d_i|`

We want to compute the derivative of the MAE with respect to `y_pred_i`. Notice that only the `i-th` term inside the summation depends on `y_pred_i`. Therefore, when we differentiate the MAE with respect to `y_pred_i`, only the `i-th` term inside the summation will be affected.

Now, let's differentiate the `i-th` term with respect to `y_pred_i`:

`d(|d_i|)/d(y_pred_i) = sign(d_i)`

The derivative of the absolute value function is the sign of its argument, which is `d_i` in this case.

Finally, we have:

`d(MAE)/d(y_pred_i) = (1/N) * sign(d_i)`

Since `d_i = y_pred_i - y_true_i`, the derivative of the MAE with respect to `y_pred_i` is:

`d(MAE)/d(y_pred_i) = (1/N) * sign(y_pred_i - y_true_i)`

This formula gives us the gradient of the MAE for each prediction `y_pred_i` with respect to the true target values `y_true_i`.
