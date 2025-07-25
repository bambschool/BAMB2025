# BAMB 2025: Reinforcement Learning

Welcome to the BAMB 2025 tutorial for the reinforcement learning module. The tutorial is divided in two parts:

1. [Basics of RL](./part1_rl_basics/)
   - Intro to structuring your RL agents and environments properly by following [gym API standards](https://github.com/Farama-Foundation/Gymnasium?tab=readme-ov-file#api)
   - Intro to RL algorithms in their simplest, tabular form
   - Extending them to classic control environments such as [CartPole](https://gymnasium.farama.org/environments/classic_control/cart_pole/)
2. [Fitting RL models to behavior](./part2_fitting_rl_models/)
   - Refresher: Basics of model fitting, selection, and recovery
   - Math: How to properly calculate likelihood for RL models
   - Brief intro to packages for fitting likelihoods for non-iid data such as in RL
   - Tutorial on fitting RL models to behavior

## Installation

We will try to run everything on Google Colab. However, if you wish to run the code locally on your machine, follow the installation instructions below.

> [!WARNING]
> If you are on Windows, we *highly* recommend installing [Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/install). Open PowerShell or Windows command prompt in administrator mode by right-clicking and selecting "Run as administrator", enter the ```wsl --install``` command, then restart your machine. Then open [VSCode](https://code.visualstudio.com/Download), hit `Ctrl + Shift + P`, and search "WSL" to select the "WSL: Connect to WSL". Check that the bottom-left of your VSCode window says "WSL: Ubuntu".

We use [Poetry](https://python-poetry.org/), a modern python packaging and dependency management software. Hopefully, this will make development a breeze and keep track of new packages that any developer installs in the pyproject.toml file. If you are unfamiliar with it, [here's a quick tutorial](https://www.youtube.com/watch?v=0f3moPe_bhk). To get started, you can use the following commands:

```sh
# clone the BAMB2025 git repository if you don't already have it
gh repo clone bambschool/BAMB2025
# if you don't have gh installed, use the git clone command below
# git clone https://github.com/bambschool/BAMB2025.git

# jump into the folder for this tutorial
cd BAMB2025/Day_2_reinforcement_learning/

# change branch to main and pull
git checkout main
git pull

# install poetry if you don't have it already
pip install poetry

# configure virtual env to be created within the project
poetry config virtualenvs.in-project true

# create the environment and install dependencies
poetry install

# activate the virtual environment
poetry shell
```

`poetry shell` is sometimes buggy (see [this](https://stackoverflow.com/questions/60580332/poetry-virtual-environment-already-activated)). If it doesn't work properly, you can activate it with `source .venv/bin/activate` if your virtual environment is in your project folder or with `source $(poetry env info --path)/bin/activate` if you don't know where it is.

## Usage

Include some examples of how to run scripts and/or notebooks.

## VS Code extensions

If you are using [VSCode](https://code.visualstudio.com/Download), which we highly recommend, install the following extensions as they would be very useful:

- [Black formatter](https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter)
- [Even Better TOML](https://marketplace.visualstudio.com/items?itemName=tamasfe.even-better-toml)
- [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [Jupyter](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)
- [Jupyter Cell Tags](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.vscode-jupyter-cell-tags)
- [Jupyter Keymap](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter-keymap)
- [Markdown all in one](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
- [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)
- [Pylance](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance)
- [Ruff](https://marketplace.visualstudio.com/items?itemName=charliermarsh.ruff)

--- 

# Resources

If you have heard of RL, you have inevitably heard of the wonderful [Sutton Barto book](http://incompleteideas.net/book/RLbook2020.pdf), which is an excellent resource to get started with. However, there are some incredibly useful resources other than books that may help you absorb the material much quicker while going deeper than the book. Here are some that I have found useful:

## Lecture series

If you're new to RL, the first ones I would recommend would be:

- [David Silver's RL course](https://youtube.com/playlist?list=PLzuuYNsE1EZAXYR4FJ75jcJseBmo4KQ9-), and
- [Martha & Adam White's RL specialization](https://www.coursera.org/specializations/reinforcement-learning#courses) if you can spare a little more time

Once you have a decent grasp of the basics, I would highly recommend the following courses from the Berkeley and Stanford giants that will surely take you to the state-of-the-art RL:

- [Pieter Abbeel's Foundations of Deep RL](https://youtube.com/playlist?list=PLwRJQ4m4UJjNymuBM9RdmB3Z9N5-0IlY0)
- [Sergey Levine's Berkeley CS285 course](https://youtube.com/playlist?list=PL_iWQOsE6TfURIIhCrlt-wj9ByIVpbfGc)
- [Chelsea Finn's Stanford CS330 course](https://youtube.com/playlist?list=PLoROMvodv4rMIJ-TvblAIkw28Wxi27B36)
- [Deep RL Bootcamp 2017](https://www.youtube.com/playlist?list=PLXoDfcPNqdnkdhRCrCCdVUOtKOwuBhJdF)

## Blogs & wikis

- [RL discord wiki](https://github.com/andyljones/reinforcement-learning-discord-wiki/wiki) hosts a ton of useful resources with many overlaps. Newcomers may want to check out their [debugging advice](https://github.com/andyljones/reinforcement-learning-discord-wiki/wiki#debugging-advice) if nothing else
- [Lilian Weng's blog posts](https://lilianweng.github.io/archives/) are an invaluable resource and service to the community
- [OpenAI Spinning up](https://spinningup.openai.com/en/latest/) is a practically-oriented tutorial/course
- [BAIR blog](https://bair.berkeley.edu/blog/about/) has monthly RL highlights from Berkeley & around
- [RL weekly](https://v1.endtoend.ai/rl-weekly/ "https://v1.endtoend.ai/rl-weekly/") is a series of weekly (not anymore) RL highlights
- [Julien Vitay's blog](https://julien-vitay.net/deeprl/)
- [Jonathan Hui's Deep RL Series on Medium](https://jonathan-hui.medium.com/rl-deep-reinforcement-learning-series-833319a95530)

## Libraries

#### RL

- [Stable Baselines 3](https://github.com/DLR-RM/stable-baselines3) is one that I have extensively used and prefer
- [RLlib](https://docs.ray.io/en/latest/rllib/index.html) is a library for large-scale distributed RL applications
- [Clean RL](https://github.com/vwxyzjn/cleanrl) is one I haven't used but heard great things about
- [My SB3 vs RLlib github repository](https://github.com/nisheetpatel/sb3-vs-rllib) benchmarking their performance and some of [my notes on working with SB3 & RLlib](https://github.com/nisheetpatel/sb3-vs-rllib/blob/main/docs/notes_sb3_vs_rllib.md)

##### Imitation Learning

- [Imitation](https://github.com/HumanCompatibleAI/imitation) has several SOTA imitation learning algorithms
- [Seals](https://github.com/HumanCompatibleAI/seals) is the sister library for imitation with all environments

#### Environments

- [Gym environments](https://gymnasium.farama.org/) (note that these were originally maintained by OpenAI but eventually Farama took over)
- [PyBullet Gym](https://github.com/benelot/pybullet-gym) open-source version of Mujoco
- [MuJoCo](https://github.com/deepmind/mujoco) the now-open-sourced physics engine for all control environments
- [MiniGrid](https://github.com/maximecb/gym-minigrid) minimalistic grid-world environments
- [MyoSuite](https://github.com/facebookresearch/myosuite) has a suite of tasks for musculoskeletal control
- [Unity ML-Agents](https://github.com/Unity-Technologies/ml-agents) enables games to serve as environments
- [ViZDoom](https://github.com/mwydmuch/ViZDoom) for Reinforcement Learning from Raw Visual Information
- [Deepmind Control suite](https://github.com/deepmind/dm_control)
- [OpenSpiel](https://github.com/deepmind/open_spiel) RL search and planning games
- [Meta-World](https://meta-world.github.io/) for multi-task meta RL
- [CARLA](http://carla.org/) open-source simulator for self-driving cars
- [PettingZoo](https://www.pettingzoo.ml/) multi-agent RL environments
- [Awesome RL environment list](https://github.com/clvrai/awesome-rl-envs)

## Additional resources for Programming in python

### Books

- [The good research code handbook](https://goodresearch.dev/index.html)
- [Learn Python the hard way by Zed Shaw](https://rupert.id.au/python/book/learn-python3-the-hard-way-nov-15-2018.pdf) 

### Arjancodes

##### Software design course + pythonic design patterns

By far, the best course out there that not only offers an introduction to the formal concepts but goes through the practical details is Arjan's [Software Design Mindset](https://www.arjancodes.com/mindset). For anyone who learns like I do, this is an absolute gem.

There is also an extension that includes Pythonic design patterns that I cannot find the link for but can highly recommend once you get through the first course.

Together, they're so comprehensive and manage to cover every aspect of modern pythonic programming. It has dramatically increased my productivity as a developer and made the whole process so much more enjoyable.

##### YouTube

If you cannot afford the course, I would still recommend [Arjancodes' YouTube channel](https://www.youtube.com/c/arjancodes). He has some fantastic videos that put the principles into practice. Some of my early favorites, before I eventually decided to take his course, were [cohesion and coupling](https://www.youtube.com/watch?v=eiDyK_ofPPM), [composition vs inheritance](https://www.youtube.com/watch?v=0mcP8ZpUR38), [SOLID design principles](https://www.youtube.com/watch?v=pTB30aXS77U), [abstraction and composition](https://www.youtube.com/watch?v=ka70COItN40&t=3s), the other videos on refactoring data science projects (pt [2](https://www.youtube.com/watch?v=Tx4AxbQNv3U), [3](https://www.youtube.com/watch?v=8fFqakxhW84)), and then some others on using [dataclasses](https://www.youtube.com/watch?v=vRVVyl9uaZc), [pydantic](https://www.youtube.com/watch?v=Vj-iU-8_xLs), [ABC vs protocol](https://www.youtube.com/watch?v=xvb5hGLoK0A&t=248s). that make OOP life easier.
