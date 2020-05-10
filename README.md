# DeepRL-LTLf
Deep Reinforcement Learning with LTLf/LDLf goals.

### Requirements
------------
*   [gym](https://github.com/openai/gym)
*   [TensorboardX](https://github.com/lanpa/tensorboardX)
*   [PyTorch](http://pytorch.org/)

### Installation of RAEnv

```
cd ra-gym
pip install -e .
```

### Installation of SAC

```
git clone https://github.com/pranz24/pytorch-soft-actor-critic
cp sac_modular.py pytorch-soft-actor-critic
```

### Train Classic SAC

```
cd pytorch-soft-actor-critic
python sac_modular.py --batch_size 64 --automatic_entropy_tuning True
```

### Train Modular SAC

```
cd pytorch-soft-actor-critic
python sac_modular.py --batch_size 64 --automatic_entropy_tuning True --modular
```






## References
- Icarte, R. T., Klassen, T., Valenzano, R., & McIlraith, S. (2018, July). Using reward machines for high-level task specification and decomposition in reinforcement learning. In International Conference on Machine Learning (pp. 2107-2116).
- Camacho, A., Icarte, R. T., Klassen, T. Q., Valenzano, R., & McIlraith, S. A. (2019, August). LTL and beyond: Formal languages for reward function specification in reinforcement learning. In Proceedings of the 28th International Joint Conference on Artificial Intelligence (IJCAI) (pp. 6065-6073).
- Toro Icarte, R., Klassen, T. Q., Valenzano, R., & McIlraith, S. A. (2018, July). Teaching multiple tasks to an RL agent using LTL. In Proceedings of the 17th International Conference on Autonomous Agents and MultiAgent Systems (pp. 452-461). International Foundation for Autonomous Agents and Multiagent Systems.
- De Giacomo, G., Iocchi, L., Favorito, M., & Patrizi, F. (2019, July). Foundations for restraining bolts: Reinforcement learning with LTLf/LDLf restraining specifications. In Proceedings of the International Conference on Automated Planning and Scheduling (Vol. 29, No. 1, pp. 128-136).
- Hasanbeig, M., Yogananda Jeppu, N., Abate, A., Melham, T., & Kroening, D. (2019). DeepSynth: Automata Synthesis for Automatic Task Segmentation in Deep Reinforcement Learning. arXiv, arXiv-1911.
- Quint, E., Xu, D., Dogan, H., Hakguder, Z., Scott, S., & Dwyer, M. (2019). Formal Language Constraints for Markov Decision Processes. arXiv preprint arXiv:1910.01074.
