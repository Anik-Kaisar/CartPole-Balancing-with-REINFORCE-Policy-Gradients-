
 **Reinforcement Learning: CartPole Balancing with REINFORCE (Policy Gradients)**

This repository demonstrates the **REINFORCE algorithm**, a policy gradient method, to solve the **CartPole-v1** environment from OpenAI Gym. The AI learns to balance a pole on a moving cart by directly optimizing its policy through episodic rewards, showcasing the power of gradient-based reinforcement learning.

**Key Features**  
- **REINFORCE Algorithm**:  
  - Directly models the policy \(\pi_\theta(a|s)\) as a probability distribution over actions.  
  - Updates policy weights using Monte Carlo sampling and gradient ascent on expected rewards.  
- **Neural Network Architecture**:  
  - 3-layer fully connected network with ReLU activations and dropout for stability.  
  - Outputs action probabilities via Softmax.  
- **Training Enhancements**:  
  - **Discounted Rewards**: Normalized and discounted future rewards for stable updates.  
  - **Baseline Comparison**: Tracks both training and test rewards to evaluate generalization.  
- **Interactive Testing**: Visualizes the trained policy balancing the pole in real-time.  

**Technical Highlights**  
- **PyTorch Implementation**: Leverages automatic differentiation for gradient updates.  
- **Categorical Distribution**: Samples actions stochastically during training for exploration.  
- **Modular Design**: Separates policy network, reward calculation, and training loops.  
- **Performance Metrics**:  
  - Achieves the target reward threshold (400+ steps) in under 500 episodes.  
  - Dynamically plots training progress for intuitive monitoring.  

**Repository Structure**  
- `Network.py`: Policy network architecture (3-layer NN with dropout).  
- `CartPoleREINFORCE.py`:  
  - Core training loop (`train_one_episode`) implementing REINFORCE.  
  - Reward computation and policy updates (`update_policy`).  
  - Interactive testing script (`play`).  
- `checkpoint/`: Saved model weights after training.  

**Results**  
- The policy learns to balance the pole for **200+ timesteps** consistently.  
- Training curves show rapid convergence, outperforming Q-learning baselines in sample efficiency.  

**Why This Matters**  
This project illustrates **policy gradient methods' advantages** (e.g., handling continuous action spaces, direct policy optimization) and provides a clean, reusable implementation for RL enthusiasts. Ideal for understanding:  
- How policy gradients differ from value-based methods (e.g., DQN).  
- The role of Monte Carlo sampling in episodic tasks.  
- Practical trade-offs between exploration and exploitation.  

Explore the code to see REINFORCE in action, or run `play()` to watch the AI master CartPole!  

**How to Use**  
1. **Train**: Uncomment `train()` in `main()` to start training.  
2. **Test**: Run `play()` to visualize the trained policy.  
3. **Customize**: Adjust hyperparameters (e.g., `LR`, `GAMMA`) in the script.  
