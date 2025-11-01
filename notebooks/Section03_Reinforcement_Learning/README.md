# Section03 — Reinforcement Learning  

## 📝 Section Review  

After mastering supervised and unsupervised learning, it’s time to teach machines how to **learn through interaction** — just like humans and animals do.  
Reinforcement Learning (RL) is where an agent learns **by trial and error**, improving its behavior through rewards and punishments from the environment.  

This section explores how machines can develop decision-making strategies in dynamic, uncertain settings — from playing games and navigating robots to optimizing control systems.  
Understanding RL not only bridges the gap between intelligence and autonomy but also lays the foundation for advanced AI systems capable of independent reasoning and adaptation.  

---

## 0️⃣ Monte Carlo Methods  

Monte Carlo algorithms rely on **experience gathered through episodes** — sequences of states, actions, and rewards — to estimate value functions.  
By repeatedly sampling and averaging outcomes, agents learn which actions lead to higher rewards, even without full knowledge of the environment’s dynamics.  
This chapter introduces how randomness can become a powerful learning tool in reinforcement-based decision processes.  

[![Open in Colab](https://img.shields.io/badge/Open%20in-Colab-F9AB00?logo=googlecolab)](https://colab.research.google.com/github/MamoMGD1/ML_101/blob/main/notebooks/Section03_Reinforcement_Learning/Chapter00_Monte_Carlo.ipynb) [![Open in Kaggle](https://img.shields.io/badge/Open%20in-Kaggle-20BEFF?logo=kaggle)](https://kaggle.com/kernels/welcome?src=https://github.com/MamoMGD1/ML_101/blob/main/notebooks/Section03_Reinforcement_Learning/Chapter00_Monte_Carlo.ipynb)

## 1️⃣ Q-Learning  

Q-Learning is a cornerstone of modern reinforcement learning — a **model-free** method that teaches agents to act optimally without knowing the environment beforehand.  
It iteratively updates a table of Q-values that represent the “quality” of each action in each state, gradually converging toward the optimal policy.  
From simple grid worlds to complex robotic control, Q-Learning demonstrates how agents can achieve intelligent behavior purely through interaction.  

[![Open in Colab](https://img.shields.io/badge/Open%20in-Colab-F9AB00?logo=googlecolab)](https://colab.research.google.com/github/MamoMGD1/ML_101/blob/main/notebooks/Section03_Reinforcement_Learning/Chapter01_Q_Learning.ipynb) [![Open in Kaggle](https://img.shields.io/badge/Open%20in-Kaggle-20BEFF?logo=kaggle)](https://kaggle.com/kernels/welcome?src=https://github.com/MamoMGD1/ML_101/blob/main/notebooks/Section03_Reinforcement_Learning/Chapter01_Q_Learning.ipynb)
