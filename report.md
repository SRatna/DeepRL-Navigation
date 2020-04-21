### Learning Algorithm

In this project, I have used DQN algorithm to train the agent.
- Basically, I created 2 networks: local and target networks.
- During the training phase, traget network is used to obtain the targeted Q-values while local network is used to get expected Q-values.
- Then, loss is calculated using MSE loss fuction.
- After that, backpropagation and optimization steps are performed.
- And finally, traget network's model parameters is changed using soft update method.
- Experience tuples necessary for training these networks are obtained from Replay memory in which newly generated experience tuple is added during the training episodes.

### Hyperparameters

Following hyperparameters are used in the project:
* BUFFER_SIZE = int(1e5) : replay buffer size
* BATCH_SIZE = 64 : minibatch size
* GAMMA = 0.99 : discount factor
* TAU = 1e-3 : for soft update of target parameters
* LR = 5e-4 : learning rate 
* UPDATE_EVERY = 4 : how often to update the network


### Network Architecture

3 Fully connected linear layers are used in both local and target networks. Relu activation fuctions are used in the outputs of input and hidden layers. First input layer is of size 37 x 64. Likewise hidden layer is of size 64 x 64 and finally output layer is of size 64 x 4. Here 37 is the number of states and 4 is number of actions.

### Plot of Rewards

#### Training Phase
Environment solved in 904 episodes with	average Score of 16.02.
![Scores during training](https://raw.githubusercontent.com/SRatna/DeepRL-Navigation/master/plots/train.png)

#### Training Phase
The average score over 100 epsoides is 14.18 during testing phase.
![Scores during testing](https://raw.githubusercontent.com/SRatna/DeepRL-Navigation/master/plots/test.png)

### Future Work

Some of advanced algorithms can be used to obtain great performance. A few of them are:
* Double DQN
* Dueling DQN
* Prioritized Experience Replay

Moreover, hyperparemeters like buffer size, learning rate and discouting rate can be changed and we can hope more improvement through it. Also, the depth of neural networks can be increase although it might increase the training time. We can also try different optimizers and see its effect in the overall performance of the agent. 