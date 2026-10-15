# Connect 4 Reinforcement Learning Agent

A Connect 4 agent trained with self-play and Double DQN in PyTorch. This was a two-person project. This repo holds my part of the work (the original notebook) and the finished, optimized agent lives in my partner's repo: [SatinWukerORIG/connect4](https://github.com/SatinWukerORIG/connect4).

**Result:** the final agent went 17-6 against a small, informal sample of human players.

## My contribution (this notebook)

The notebook (`Connect4AgentNotebook.ipynb`, also available on [Colab](https://colab.research.google.com/drive/1EObVRj4g9vdMKxz2Y8wprC7yCO_lEv2X?usp=sharing)) is a first working version of the full learning pipeline, guided by the [PyTorch Reinforcement Q-Learning tutorial](https://docs.pytorch.org/tutorials/intermediate/reinforcement_q_learning.html).

- **Game environment:** a simulated Connect 4 environment whose step function returns the action, next state, and reward.
- **Replay buffer:** transitions from the environment are stored in a replay buffer and sampled to train the network.
- **Double DQN:** Q-values are computed with a Double DQN. A lagging target network is used to update the policy network, so training doesn't update too fast or overfit.
- **Self-play:** basic self-play using shared-memory queues.
- **Interface:** HTML rendering of the board inside the notebook, plus player input so a human can play against the agent.

## Partner's contribution

My partner took the notebook and turned it into the final agent:

- Added checkpoint saving in the notebook, then moved the code to VS Code
- Improved self-play: saving effective checkpoints, running mini tournaments to pick the strongest model, and continuing training from the best ones
- Added a low-depth minimax opponent to speed up training
- Changed core design decisions, including switching the network from an MLP to a CNN and the board representation to 7x7x2, which greatly improved the agent's strength

## Links

- [Finished repo (partner)](https://github.com/SatinWukerORIG/connect4)
- [Original notebook on Colab](https://colab.research.google.com/drive/1EObVRj4g9vdMKxz2Y8wprC7yCO_lEv2X?usp=sharing)
- [Project presentation](https://docs.google.com/presentation/d/1XvvnGEofifwIAULLLDYKeIypsNskkx9uJw-ZUGeo6rc/edit?usp=sharing)
