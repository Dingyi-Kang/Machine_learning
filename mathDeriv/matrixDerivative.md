# first note: the derivative respect to scalar is different from the derivative respect to matrix in certain ways.
## in short:
    For the following example:
    L = |y - y_hat| 
    y_hat = f(a)
    a = W * x + b
    We already know ∂L/∂a, then we have:
    ∂L/∂W = ∂L/∂a @ x.T 
    ∂L/∂x = W.T @ ∂L/∂a

    As for the activation "layer", we use scalar/element-wise matrix multiplication:
    ∂L/∂a = ∂L/∂y_hat * f'(a)
    (because, in essence, activation function is (should be) a non-linear translation of each elements of the input matrix. Hence, its derivative is also a one-to-to map)


## for example in maxtrix cookbook (https://www.math.uwaterloo.ca/~hwolkowi/matrixcookbook.pdf):
<img width="660" alt="image" src="https://user-images.githubusercontent.com/81428296/235757149-d773db7f-3702-4e69-b5fc-0d166e969fbe.png">

## Then, this tutorial is very very good: https://www.youtube.com/watch?v=GlcnxUlrtek

### for instance, ∂L/∂W can be understood as back propagating the error (gradient of loss respect to a in this example) to each weight (assume the s/x are constant)
<img width="677" alt="image" src="https://user-images.githubusercontent.com/81428296/235760100-4325e263-b601-470f-8e45-046b9dea2b82.png">

<img width="705" alt="image" src="https://user-images.githubusercontent.com/81428296/235759471-3e691185-d07b-4c31-a175-825a75f22424.png">

