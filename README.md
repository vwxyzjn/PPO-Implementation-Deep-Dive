# PPO-Implementation-Deep-Dive

This repo contains the source code for the [PPO Implementation Deep Dive] tutorial series. 
You can find out where theses implementation details come from by visiting 
my [blog post](https://costa.sh/blog-the-32-implementation-details-of-ppo.html), which contains
github permanent links of the details to the original implementation.


### Get started

(Optional) Setup virtual environments:
```
pyenv install -s $(sed "s/\/envs.*//" .python-version)
pyenv virtualenv $(sed "s/\/envs\// /" .python-version)
```

Install dependencies:
```
poetry install
```

Train agents:
```
python ppo.py
```

Train agents with experiment tracking:
```
python ppo.py --track --capture-video
```

## Atari
Install dependencies:
```
poetry install -E atari
AutoROM
```
Train agents:
```
python ppo_atari.py
```
Train agents with experiment tracking:
```
python ppo_atari.py --track --capture-video
```