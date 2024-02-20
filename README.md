Reinforcement Learning for Acrobot-v1

Introduction

Reinforcement Learning (RL) involves creating intelligent agents that learn optimal behavior through trial-and-error in a specific context. In this project, we implemented RL using Deep Q-Learning to train an agent to play the Acrobot-v1 game from OpenAI Gym. The Acrobot environment features a two-link robotic arm with the goal of raising the lower link's end to a certain height in an upright position.

RL Model Implementation

We utilized PyTorch to implement Deep Q-Learning, focusing on a deterministic policy to estimate future returns. The state of the agent consists of four observations related to angular velocities and sine/cosine of joint angles, influencing the speed and momentum of the arm's swing. Actions are torque applied to the joints, determining the arm's motion.

Action Space and Reward Function

The action space comprises three discrete values (-1, 0, 1), representing the torques applied to the two joints. The reward function ranges from -500 to 0, with -500 indicating the lowest reward, and 0 representing success. The agent learns to optimize torque actions, developing velocity to control the arm's position and stabilize the second link.

DQN Algorithm

We employed a Deep Q-Network (DQN) for learning optimal policies. The agent interacts with the environment, and experiences (state, action, reward, next state) are stored in a replay memory. The DQN model predicts Q-values for each action, and training involves updating the model's parameters to maximize cumulative rewards. Policy exploration and exploitation are balanced using an epsilon-greedy strategy.

Update Rule

The DQN update rule adheres to the Bellman equation, relating the value of a state or action to future values. The learning rate determines the weight given to new information, and a target network helps stabilize learning by using delayed updates.

Results

Rewards during Training

The agent was trained for 1000 episodes, showing an initial exploration phase with random actions. Average rewards improved after ~100 episodes, converging to stable performance. Deep drops in rewards indicate exploration attempts, with the model eventually reaching an average reward of -102.537.

Agent Performance during Testing

During testing (250 episodes), the agent achieved an average reward of -59.906, demonstrating its ability to consistently reach the goal. Notably, the model showed exploitation behavior, avoiding deviation from learned policies.

Conclusion

This project successfully implemented RL using DQN for the Acrobot-v1 environment. The agent learned to control the robotic arm, achieving improved performance over training episodes. Further analysis and comparisons with alternative algorithms could enhance our understanding of the agent's capabilities. The trained model showcased the effectiveness of RL in solving complex control problems, providing a foundation for future research and applications.
