# PPO-Implementation-Deep-Dive

This repo contains the source code for the [PPO Implementation Deep Dive] tutorial series. 
You can find out where theses implementation details come from by visiting 
my [blog post](https://costa.sh/blog-the-32-implementation-details-of-ppo.html), which contains
github permanent links of the details to the original implementation.


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
```
Train agents:
```
poetry run python ppo_atari.py
```
Train agents with experiment tracking:
```
poetry run python ppo_atari.py --track --capture-video
```

A quick note on Atari reproducibility:

Since [`gym==0.20.0`](https://github.com/openai/gym/releases/tag/v0.20.0), the original `atari-py` dependency has been deprecated in favor of `ale-py`, which is a "massive and breaking upgrade, please see [explainer TBD]", which breaks the reproducibility of the atari experiments. When using `gym==0.20.0`, our `ppo_atari.py` would roughly get <200 episodic returns for Breakout, whereas using `gym==0.19.0` would gain ~400 episodic returns (shown in our video). You can see this [report](https://wandb.ai/costa-huang/cleanRL/reports/ALE-py-vs-atari-py--VmlldzoxMDE1NDM4) for the performance difference. 


I'd normally recommend to use the latest release because it fixes many problems of `atari-py`, but in the interest of reproducibility to past works, I would favor `gym==0.19.0` for this tutorial. However, since I also need the `NormalizeObservation` and `NormalizeReward` wrapper in the new release (see https://github.com/openai/gym/pull/2387), I have installed a specific commit in poetry (i.e. `gym @ git+https://github.com/openai/gym.git@b1b00861345876dd4b9aa7908efaedfe40fe04c5`).
