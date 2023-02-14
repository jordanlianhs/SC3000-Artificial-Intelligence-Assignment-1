# SC3000-Assignment-1 (Balancing a pole on a cart)

As shown in the figure below, a pole is attached by an un-actuated joint to a cart, which moves along a frictionless track. The pendulum is placed upright on the cart and the goal is to balance the pole by applying forces in the left and right direction on the cart. In this project, you will need to develop a Reinforcement Learning (RL) agent. The trained agent makes the decision to push the cart to the left or right based on the cart position, velocity, and the pole angle, angular velocity.
 
![Picture 1](https://user-images.githubusercontent.com/97859704/218644872-e8ed5b58-e5a3-4000-9336-1368cd8c1428.gif)

Figure 1. Balancing a pole on a cart.

# Problem instance

You are given an instance of the cart pole environment implemented by the gym library. A step-by-step tutorial on installing, loading, and using the CartPole environment is included in https://github.com/yue-zhongqi/cartpole_colab. You will use Jupyter notebook, an interactive, and what-you-see-is-what-you-get python script environment, which is widely used in AI research community. Before starting this project, please go to https://docs.jupyter.org/en/latest/ and https://colab.research.google.com/notebooks/basic_features_overview.ipynb#scrollTo=KR921S_OQSHG for some hands-on examples.

A summary of the pole cart environment is given below:

Action Space
The action is an ndarray with shape (1,) which can take values {0, 1} indicating pushing the cart to the left or right, respectively. Note that the velocity that is reduced or increased by the applied force is not fixed and it depends on the angle the pole is pointing. The center of gravity of the pole varies the amount of energy needed to move the cart underneath it.

Observation Space
The observation is an ndarray with shape (4,) with the values corresponding to the following positions and velocities:

Num	Observation	Min	Max
0	Cart Position	-4.8	4.8
1	Cart Velocity	-Inf	Inf
2	Pole Angle	~ -0.418 rad (-24°)	~ 0.418 rad (24°)
3	Pole Angular Velocity	-Inf	Inf

Reward
Since the goal is to keep the pole upright for as long as possible, a reward of +1 for every step taken, including the termination step, is allotted.

Starting State
All observations are assigned a uniformly random value in (-0.05, 0.05).

Episode End
The episode ends if any one of the following occurs:
Termination: Pole Angle is greater than ±12°
Termination: Cart Position is greater than ±2.4 (center of the cart reaches the edge of the display)
Truncation: Episode length is greater than 500.
