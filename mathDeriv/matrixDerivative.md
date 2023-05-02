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

## for instance, ∂L/∂x can be understood as back propagating the error (i.e., the gradient of loss respect to 'a' in this example) to each weight 
### (assume the weight mtrix W is constant, then by multipling transpose of W with ∂L/∂a, we can get a matrix which represents the contribution of each x on ∂L/∂a)
<img width="968" alt="image" src="https://user-images.githubusercontent.com/81428296/235766531-f457bbae-8ee5-4d2b-b515-d8a7c9088c05.png">
<img width="1018" alt="image" src="https://user-images.githubusercontent.com/81428296/235766276-bc7f9873-66b0-489e-9be8-4594f47763a8.png">
<img width="677" alt="image" src="https://user-images.githubusercontent.com/81428296/235760100-4325e263-b601-470f-8e45-046b9dea2b82.png">
<img width="705" alt="image" src="https://user-images.githubusercontent.com/81428296/235759471-3e691185-d07b-4c31-a175-825a75f22424.png">

<img width="971" alt="image" src="https://user-images.githubusercontent.com/81428296/235765913-5aef7ba3-f12d-4810-a94c-b4a1d5994e58.png">
<img width="962" alt="image" src="https://user-images.githubusercontent.com/81428296/235765990-1d77035d-2528-4d57-8569-f4da35d2cad3.png">
<img width="1036" alt="image" src="https://user-images.githubusercontent.com/81428296/235766219-24812fb6-5672-4bf4-bb19-e9f51da9b560.png">
