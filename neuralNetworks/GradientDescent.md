## Link to the great tutorial: https://youtu.be/sDv4f4s2SB8

## below is the example of gradient descent with the loss function of sum square residuals(SSR)

### 1. we take derivatives of the SSR with respect to each parameter (including the constant bias) so as to calculate the step size of learning

### 2. we take the derivatives of the SR with respect to each parameter on each data point (x1, x2, ... xn and y1, y2, ... yn)

### 3. we sum up the derivatives of the SR with respect to a certain parameter on all data point and get the derative of SSR with respect to this parameter

### 4. of course, we can use chain rule to simplify the derivative equation
<img width="1329" alt="image" src="https://user-images.githubusercontent.com/81428296/193479151-b9536eca-3bc6-4fc0-858d-db8fa734b37d.png">

<img width="1268" alt="image" src="https://user-images.githubusercontent.com/81428296/193479242-97540005-68d5-49db-a3ad-49fc14bdda61.png">
<img width="1319" alt="image" src="https://user-images.githubusercontent.com/81428296/193479270-31da2f74-0406-46c1-9822-c7a60391de33.png">
<img width="1352" alt="image" src="https://user-images.githubusercontent.com/81428296/193479286-5e431c9e-8ffd-4914-abec-7902eb0bb7a2.png">

## when gradient descent stops
### 1. when the step size is very close to 0
### 2. when the maximum of steps is reached
<img width="667" alt="image" src="https://user-images.githubusercontent.com/81428296/193479363-c66e609a-080e-4333-b091-327e4b062097.png">
<img width="683" alt="image" src="https://user-images.githubusercontent.com/81428296/193479379-44a48f72-7020-416c-93d7-cb71607db80b.png">

## the case of getting the derivative of SSR with repspect to a parameter instead of constant bias
<img width="1327" alt="image" src="https://user-images.githubusercontent.com/81428296/193479537-f450a4cc-b94f-45b4-bc3b-640efe1c6b6c.png">

## for the cases of more than one parameters, we get the derivatives of SSR with respect to each parameter and get corresponding step size for each parameter and update each parameter seperately
### in the process of calculating the derative of SSR with respect to a parameter, we view other parameter as constant
<img width="1350" alt="image" src="https://user-images.githubusercontent.com/81428296/193479563-2bf2c421-e8c1-4fc4-9983-42c6983d01dd.png">

<img width="550" alt="image" src="https://user-images.githubusercontent.com/81428296/193479667-f3a8994d-2ae0-45ee-9fa4-3bfe8ad81e8a.png">

<img width="572" alt="image" src="https://user-images.githubusercontent.com/81428296/193479695-212fceac-8e0c-4297-91fc-1015edad3ea2.png">
<img width="1307" alt="image" src="https://user-images.githubusercontent.com/81428296/193479727-7408e25a-746c-40ac-9484-7c6e9a57d9d3.png">
<img width="1366" alt="image" src="https://user-images.githubusercontent.com/81428296/193479792-6f66edaa-8e60-411a-b7b4-6dbf23a4ffbb.png">
<img width="1366" alt="image" src="https://user-images.githubusercontent.com/81428296/193479811-978163f7-e31a-4271-9c4e-c4cc8880b3d7.png">

