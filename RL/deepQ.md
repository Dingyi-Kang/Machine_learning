First part of this below tutorial explains Deep Q learning

https://www.youtube.com/watch?v=ELE2_Mftqoc&t=295s


## Deep Q learning traditionally keep a table of stata and action paris (dictionary in python). Hence, it only applied to the case where there are finite discrete actionsa and states
## Different from policy gradient which learn after each episode, Deep Q learns after each timestamp
## It needs to keep the history

## if the environment has a huge number of states, or the state is continues, we need to rely on a deep neural network (instead of a table) to turn these observations of env into discrete outputs that corresponse to the value of each action. That is called Deep Q Learning
