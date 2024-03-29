# DeepRL-LTL
The repository implements a Reinforcement Learning Task on a custom environment using temporal logic specifications. The project is based on the paper "[Modular Deep Reinforcement Learning with Temporal Logic Specifications](https://arxiv.org/abs/1909.11591)" (Lim Zun Yuan et al.) using a modified Soft-Actor-Critic algorithm based on the Py-Torch implementation provided at [Py-Torch SAC](https://github.com/pranz24/pytorch-soft-actor-critic).

[Project Webpage](https://rickymexx.github.io/DeepRL-LTL/)

<br>

## Table Of Contents
*   [The Environment](#the-environment)
*   [Results](#results)
*   [Installation](#installation)
*   [References](#references)

<br>

## The Environment
The task is performed on a custom environment developed using Gym-OpenAI and consists in the agent (the ball) going through the two circles in a specified order: bottom-left, top-right. The 6-dimensional state consists of the position and velocity along the x and y axes and two binary values (one for each circle) specifying whether the agent has gone through a circle. 

![sac_only](/img/env.png)

<br>

## Results
Two agents have been trained on the task: one given by the "classic" SAC algorithm with no modification, while a second one trained as described in the paper (Lim Zun Yuan et al. [1]) with a modular design that separates the task in two sub-goals. 

![Reward](/img/reward.png)
<br><br>

---------------------

We show how SAC alone (on the left) can easily reach the first goal but fails to reach the second even though the state provides the agent with the information about having reached the first circle. The modular agent (on the right), instead, is able to completely solve the specified task.


![sac_only](/img/sac_only.gif)
![sac_modular](/img/sac_modular.gif)


<br>

## Installation

<br>

### Requirements
*   [gym](https://github.com/openai/gym)
*   [TensorboardX](https://github.com/lanpa/tensorboardX)
*   [PyTorch](http://pytorch.org/)

<br>

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

<br><br>

## Presentation

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vStkrVtoZyBgFP3kJ4hAQnWD4J9zsNRZXeU1I5B62CZHfRseHD5lXUkfp-OWOwcOh6xJvjsozc92kEN/embed?start=false&loop=true&delayms=3000" frameborder="0" width="960" height="749" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

<br><br>

## Credits
- [Caprari Riccardo](https://github.com/RickyMexx)
- [Giacomini Emanuele](https://github.com/EmanueleGiacomini)
- [Ragno Alessio](https://github.com/spideralessio)
- [Savoia Dylan](https://github.com/dylansavoia)


<br>


## References
- Lim Zun Yuan, Mohammadhosein Hasanbeig, Alessandro Abate, and Daniel Kroening. Modular Deep Reinforcement Learning with Temporal Logic Specifications. Department of Computer Science, University of Oxford.
- Mohammadhosein Hasanbeig, Alessandro Abate, and Daniel Kroening. Certified Reinforcement Learning with Logic Guidance.
- Icarte, R. T., Klassen, T., Valenzano, R., & McIlraith, S. (2018, July). Using reward machines for high-level task specification and decomposition in reinforcement learning. In International Conference on Machine Learning (pp. 2107-2116).

