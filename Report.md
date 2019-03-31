
[image1]: ./result.png 'Training Result'

# Project 3: Collaboration and Competition

### Algorithm Overview

The agent model is based on the Deep Deterministic Policy Gradients (DDPG) algorithm, which leverages the Actor-Critic networks. Both agents share the same Actor and Critic models. After tuning hyper-parameters the environment has been solved with N episodes.

#### The Actor network hyper-parameters:

- Hidden layers: 1 
- 1st hidden layer nodes (FC): 256 
- Output layer nodes (actions): 4 
- Input parameters (states): 24 
- Activation function: ReLU (except output - tanh) 

#### The Critic network hyper-parameters:

- Hidden layers: 3 
- 1st hidden layer nodes (FC): 256 
- 2nd hidden layer nodes (FC): 256 
- 3nd hidden layer nodes (FC): 128 
- Output layer nodes (Q-value): 1 
- Input parameters (states): 24 
- Activation function: ReLU

### Training

The agent model was trained on local machine with GPU. The following hyper-parameters were used:

- Optimizer: Adam 
- Replay buffer size: 1e6 
- Minibatch size: 1024 
- Discount factor (Gamma): 0.99 
- Learning rate (Actor): 1e-3 
- Learning rate (Critic): 1e-4 
- L2 weight decay: 0 
- Tau: 1e-3

### Result

I solved the environment in 1406 episodes of total 1500. Scores are shown on fig. 1.

```
Episode 1390 Average Score: 0.41 
Episode 1400 Average Score: 0.44 
Enviroment solved in @ i_episode=1406, w/ avg_score=0.50 
Episode 1410 Average Score: 0.55 
... 
Episode 1500 Average Score: 1.89
```

![Training Result][image1]

### Future Ideas
To improve the agent's performance the following techniques can be used:

* examine MADDPG (separate Actor/Critic) and tune hyper-parameters
* change network layers/nodes and choose different hyper-parameters
* try other algorithms like PPO, A3C or D4PG
* use prioritised experience buffer