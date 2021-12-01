# PPO-Implementation-Deep-Dive

This repo contains the source code for the PPO Implementation Deep Dive tutorial series. 

1. Proximal Policy Optimization Implementation Deep Dive | 11 Core Implementation Details [youtu.be/MEt6rrxH8W4](https://youtu.be/MEt6rrxH8W4)
2. Proximal Policy Optimization Implementation Deep Dive | 9 Atari-specific Details [youtu.be/05RMTj-2K_Y](https://youtu.be/05RMTj-2K_Y)
3. Proximal Policy Optimization Implementation Deep Dive | 8 Details for Continuous Actions [youtu.be/BvZvx7ENZBw](https://youtu.be/BvZvx7ENZBw)

![image](https://user-images.githubusercontent.com/5555347/144305162-435cf10f-780a-4681-bb7e-95b84f4e0146.png)



You can find out where theses implementation details come from by visiting 
my [blog post](https://costa.sh/blog-the-32-implementation-details-of-ppo.html), which contains
github permanent links of the details to the original implementation.

If you like this repo, consider also checking out [CleanRL](https://github.com/vwxyzjn/cleanrl), my RL library based on single-file implementations.


## Get started

Prerequisites:
* Python 3.8+
* [Poetry](https://python-poetry.org)

Install dependencies:
```
poetry install
```

Train agents:
```
poetry run python ppo.py
```

Train agents with experiment tracking:
```
poetry run python ppo.py --track --capture-video
```

### Atari
Install dependencies:
```
poetry install -E atari
poetry run AutoROM
```
Train agents:
```
poetry run python ppo_atari.py
```
Train agents with experiment tracking:
```
poetry run python ppo_atari.py --track --capture-video
```


### Pybullet
Install dependencies:
```
poetry install -E pybullet
```
Train agents:
```
poetry run python ppo_continuous_action.py
```
Train agents with experiment tracking:
```
poetry run python ppo_continuous_action.py --track --capture-video
```
