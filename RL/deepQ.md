First part of this below tutorial explains Deep Q learning

https://www.youtube.com/watch?v=ELE2_Mftqoc&t=295s


## Deep Q learning traditionally keep a table of stata and action paris (dictionary in python). Hence, it only applied to the case where there are finite discrete actionsa and states
## Different from policy gradient which learn after each episode, Deep Q learns after each timestamp
## It needs to keep the history

## if the environment has a huge number of states, or the state is continues, we need to rely on a deep neural network (instead of a table) to turn these observations of env into discrete outputs that corresponse to the value of each action. That is called Deep Q Learning. The deep neural network act as a universal function approximators.


## It needs to train two deep neural networks -- one is evaluation network (evaluate the current state and to see which action to take) while the other is target network which is used to calculated the values of maximum action during the learning step

## by just a frame/scene, it is hard to tell the motion of the object. Hence, we need a way of stacking frames to give agent a sense of motion
## hence, if the inputs are image/pixels, the CNN takes in the batch of stacked images as input rather than a single image
