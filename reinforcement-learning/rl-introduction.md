# RL Introduction

## Textbook: Reinforcement Learning An Introduction

 _one of the most popular Reinforcement Learning book by **Richard S. Sutton** and **Andrew G. Barto** \(_2nd Edition\)_. The book can be found here:_ [_Link_](http://incompleteideas.net/book/the-book-2nd.html)_._

{% embed url="https://web.stanford.edu/class/psych209/Readings/SuttonBartoIPRLBook2ndEd.pdf" %}



## Overview of Reinforcement Learning

RL is teaching BY experience. A good strategy for an agent would be to always choose an action that maximizes the \(discounted\) future reward

Defining a useful state space, action space and reward are hard part. Getting meaningful data fro the formalization is very hard. 

### Environment and Actions

![Deep RL lecture -MIT](../images/image%20%2865%29.png)

Challenge in RL in real-world applications are how to provide the experience? One option is providing Realistic simulation + transfer learning 

#### Components of RL agent

![](../images/image%20%2861%29.png)

### Maximize the reward

A good strategy for an agent would be to always choose an action that maximizes the \(discounted\) future reward

![](../images/image%20%2886%29.png)

### Optimal Policy

Both Environment model and Reward structures have big impact on optimal policy



### Types of Reinforcement Learning

It can be classified either Model-based or Model-Free

* Model-based: e.g. Chess etc
* Model-free
  * Value-based: Off-Policy, can choose the best action. Example: Q-Learning
  * Policy-based: On-Policy, Directly learn the best policy

![](../images/image%20%2823%29.png)

![](../images/image%20%2868%29.png)

#### Q-Learning \(Deep Q-Learning Network\)

It is a Model-Free, Off-Policy, Value-based Method

![](../images/image%20%2846%29.png)

A conventional method of Q-Learning, it is basically a Q-table that updates. But it is not practical with limited rows/cols of table.

Deep Q-Learning uses a neural network to approximate the Q-Function.  This does not require to know and understand the physics of the environment. 

![](../images/image%20%2854%29.png)

![](../images/image%20%2880%29.png)

![](../images/image%20%2860%29.png)

### Policy Gradient

![](../images/image%20%2832%29.png)

Vanilla Policy Gradient

![](../images/image%20%2867%29.png)

#### Advantage Actor-Critic \(A2C\)

Combined DQN and REINFORCE

![](../images/image%20%2824%29.png)

#### Deep Deterministic Policy Gradient \(DDPG\)

![](../images/image%20%2874%29.png)

![](../images/image%20%2828%29.png)

![](../images/image%20%2841%29.png)

