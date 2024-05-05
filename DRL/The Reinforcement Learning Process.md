![[Pasted image 20240208204655.png]]

to understand the rl process we can visualize the agent to play a platformer

![[Pasted image 20240208204740.png]]

the process of rl goes like this
- the agent receives the initial state of the environment
- based on the initial state the agent takes an action
- based on this action the environment changes to a new state
- based on the environment change the agent is either reward (+1 point) or punished (-1 point)

![[Pasted image 20240208205108.png]]

the agent is expected to try to maximise its total no. of points this is called the _**expected reward**

### the reward hypothesis

all goals can be described as the maximisation of the expected return (expected cumulative reward).

### Markov property

In papers, the RL process is referred to as the "Markov Decision process" (MDP).

it implies that our agent only requires the current state of the environment and not the history of all the states and actions they took before.

### Observations / States

this is the information that the agents get from the environment
Ex: frame of a game, value of a stock at a certain time, etc.

*State s:* the complete description of the environment / state of the world (no hidden info). The agent can fully observe the environment.

*Observation o:* partial description of the environment / state of the world (hidden info). The agent cannot fully observe the evironment.

### Action space

the action space is the set of all possible events / actions in an environment

there are 2 types
- discrete action space
- continuous action space

*discrete action space:* the no. of actions is **finite.**
Ex: super mario bros controls (only 4 to move and jump)

*continuous action space:* the no. of actions is **infinite.**
Ex: self driving car has infinite no. of possible actions

### Reward and discounting

*Reward*: the only feedback that the agent gets. Thanks to the reward the agent can understand whether the action it took was good / bad.

![[Screenshot 2024-05-05 at 9.40.27 PM.png]]
(or)

![[Screenshot 2024-05-05 at 9.40.47 PM.png]]

However, in reality we cannot just add them together like that

![[Screenshot 2024-05-05 at 9.42.42 PM.png]]

*Discount rewards:* 
- we define a discount rate, gamma. It must be b/w 0 and 1. Most of the times b/w 0.95 to 0.99
- the larger the gamma value, the smaller the discount. This means our agent cares more about the long term reward
- on the other hand, the smaller the gamma, the bigger the discount. This means our agent cares about the short term reward (the nearest cheese).

![[Screenshot 2024-05-05 at 9.45.44 PM.png]]

### tasks
A task is an instance of a RL problem.
2 types
- episodic
- continuing

*episodic:* this type of task has a starting point and ending point.

For instance, think about Super Mario Bros: an episode begin at the launch of a new Mario Level and ends **when you’re killed or you reached the end of the level.** 

*continuing:* this type of task has no ending.
the agent must learn to choose the best actions and simultaneously interact with the env.

For instance, an agent that does automated stock trading. For this task, there is no starting point and terminal state. **The agent keeps running until we decide to stop it.**