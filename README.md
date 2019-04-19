[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/42135619-d90f2f28-7d12-11e8-8823-82b970a54d7e.gif "Trained Agent"

# Project 1: Navigation

### Project Details

For this project, the agent will be trained to navigate (and collect bananas!) in a large, square world.  

![Trained Agent][image1]

- A reward of +1 is provided for collecting a yellow banana, 
- A reward of -1 is provided for collecting a blue banana.  

Thus, the goal of your agent is to collect as many yellow bananas as possible while avoiding blue bananas.  

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around agent's forward direction.  Given this information, the agent has to learn how to best select actions.  Four discrete actions are available, corresponding to:
- **`0`** - move forward.
- **`1`** - move backward.
- **`2`** - turn left.
- **`3`** - turn right.

The task is episodic, and in order to solve the environment, the agent must get an average score of +13 over 100 consecutive episodes.

### Getting Started
1. Create (and activate) a new environment with Python 3.6.

	- __Linux__ or __Mac__: 
	```bash
	conda create --name drlnd python=3.6
	source activate drlnd
	```
	- __Windows__: 
	```bash
	conda create --name drlnd python=3.6 
	activate drlnd
	```

2. Install these dependencies in the environment (My environment was windows 10).
	- __Install Unity ML-Agents__
	```bash
	pip3 install --user mlagents
	```	
	- __Install Unity Agents__
	```bash
	pip install unityagents
	```	
	- __Install Pytorch__
	```bash
	conda install pytorch torchvision cudatoolkit=9.0 -c pytorch
	```
	
3. Download the Banana environment from one of the links below.  You need only select the environment that matches your operating system:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux_NoVis.zip) to obtain the environment.

4. Unzip (or decompress) the file in the `p1_navigation/` folder

(**Note**: the project is built locally successfully but the training took long so i used Udacity workspace with GPU enabled.)

### Instructions

1. Copy both files **dqn_agent.py** and **model.py** from `dqn/solution` folder into the project folder `p1_navigation/`
	- [click here] (https://github.com/udacity/deep-reinforcement-learning/tree/master/dqn/solution)
 
2. To run the agent, three subsequent cells are added into `Navigation` notebook:
	- Cell for the instaniation of the agent and the reset of the environment
	```bash
	agent = Agent(state_size=state_size, action_size=action_size, seed=0)
	env_info = env.reset(train_mode=True)[brain_name]
	```

	- Cell for running and train the agent
	```bash
	def dqn(n_episodes=2000, max_t=1000, eps_start=1.0, eps_end=0.01, eps_decay=0.995):
	.
	.
	.
	scores = dqn()
	```
	
	- Cell for plotting the `average scores per 100 episodes` against the `Episode #`"# navigation" 
