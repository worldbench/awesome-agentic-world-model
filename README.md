[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome) [![PR's Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat)](https://github.com/worldbench/awesome-agentic-world-model/pulls) ![Visitors](https://visitor-badge.laobi.icu/badge?page_id=worldbench.awesome-agentic-world-model&left_color=gray&right_color=blue) [![arXiv](https://img.shields.io/badge/arXiv-XXXX.XXXXX-b31b1b?style=flat&logo=arxiv)](#)

# Awesome Agentic World Modeling

This repository accompanies the position paper **"Quo Vadis, World Modeling? Towards Interactive World Proxies for Continually Improving Agents."** It curates the works discussed in the survey and argues for a shift in world modeling: from a **World Model** that passively predicts the next physical state, toward an **Agent-Centric World Proxy** — an environment-grounded interface that returns the *information transition* an agent needs (a future state, a rendered view, an execution result, a retrieved memory or skill, or a verdict on a plan) to plan, learn, and continually improve.

The taxonomy has two orthogonal axes. **Six proxy functions** describe *what* feedback the proxy returns — **Dynamics**, **Spatial**, **Execution**, **Memory / Experience**, **Skill**, and **Reward / Verification** — and **three empowerment levels** describe *how* the proxy improves the agent: <kbd>L1</kbd> inference-time guidance, <kbd>L2</kbd> training-time optimization, and <kbd>L3</kbd> Agent–Proxy co-evolution.

## Citation

If you find this work useful, please consider citing:

```bibtex
@article{yang2026worldproxy,
  title   = {Quo Vadis, World Modeling? Towards Interactive World Proxies for Continually Improving Agents},
  author  = {Yang, Yu and Yang, Xuemeng and Wen, Licheng and Kong, Lingdong and Zhang, Jiangning and Hu, Xiaobin and Lu, Dongyue and Chow, Wei and others},
  journal = {arXiv preprint arXiv:XXXX.XXXXX},
  year    = {2026}
}
```
<!-- TODO: replace XXXX.XXXXX with the arXiv ID and the badge/link above once the paper is posted. -->

## Call for Contributions

Agentic world modeling moves fast, and the boundary between a passive *world model* and an agent-facing *world proxy* is still being drawn. This list aims to be a living, community-maintained map of that space — contributions of new work, and corrections, are very welcome.

To contribute, open an issue or a pull request:

- **Where:** add each entry to the section matching its proxy function (or the closest one), and keep every table in chronological order.
- **Format:** follow the existing row layout — a short model name in `Model` (or `-` if none), the title with an arXiv badge in `Paper`, and the abbreviated venue with year in `Venue`.
- **Verify:** check the title, authors, arXiv ID, and venue against the primary source before adding, and prefer the formally published version whenever one exists.
- **Fix:** corrections to venues, broken links, or mis-categorized entries are equally welcome — flag them in an issue or fix them directly in a pull request.

## Table of Contents

- [Background](#background)
  - [Classical World Models & Model-Based RL](#classical-world-models--model-based-rl)
  - [Continual Improvement & Interaction Cost](#continual-improvement--interaction-cost)
- [The Six Proxy Functions](#the-six-proxy-functions)
  - [Dynamics Proxy](#dynamics-proxy)
  - [Spatial Proxy](#spatial-proxy)
  - [Execution Proxy](#execution-proxy)
  - [Memory, Experience & Skill Proxy](#memory-experience--skill-proxy)
  - [Reward / Verification Proxy](#reward--verification-proxy)
- [Empowerment Levels (L1 / L2 / L3)](#empowerment-levels-l1--l2--l3)
- [Evaluation, Fidelity & Safety](#evaluation-fidelity--safety)
- [Surveys & Related Work](#surveys--related-work)
- [Additional References](#additional-references)


# Background

## Classical World Models & Model-Based RL

Foundations: state-transition world models and model-based RL that predict the next physical state given a state and an action.

| Model | Paper | Venue |
|:-:|:-|:-:|
||
| `-` | Dyna, an integrated architecture for learning, planning, and reacting | SIGART 1991 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-1803.10122-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/1803.10122)<br>Recurrent World Models Facilitate Policy Evolution | NeurIPS 2018 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-1906.08253-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/1906.08253)<br>When to Trust Your Model: Model-Based Policy Optimization | NeurIPS 2019 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-1912.01603-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/1912.01603)<br>Dream to Control: Learning Behaviors by Latent Imagination | ICLR 2020 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-1911.08265-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/1911.08265)<br>Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model | Nature 2020 |
| `-` | A Path Towards Autonomous Machine Intelligence | OpenReview preprint 2022 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2006.16712-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2006.16712)<br>Model-Based Reinforcement Learning: A Survey | FTML 2023 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2301.04104-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2301.04104)<br>Mastering diverse control tasks through world models | Nature 2025 |


## Continual Improvement & Interaction Cost

Why real-environment interaction alone cannot carry continual improvement — cost, safety, latency, and the need for scalable feedback.

| Model | Paper | Venue |
|:-:|:-|:-:|
||
| `MuJoCo` | MuJoCo: A Physics Engine for Model-Based Control | IROS 2012 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2108.10470-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2108.10470)<br>Isaac Gym: High Performance GPU-Based Physics Simulation for Robot Learning | NeurIPS 2021 |
| `DayDreamer` | [![arXiv](https://img.shields.io/badge/arXiv-2206.14176-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2206.14176)<br>DayDreamer: World Models for Physical Robot Learning | CoRL 2023 |
| `CodeIt` | [![arXiv](https://img.shields.io/badge/arXiv-2402.04858-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2402.04858)<br>CodeIt: Self-Improving Language Models with Prioritized Hindsight Replay | ICML 2024 |
| `Voyager` | [![arXiv](https://img.shields.io/badge/arXiv-2305.16291-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2305.16291)<br>Voyager: An Open-Ended Embodied Agent with Large Language Models | TMLR 2024 |
| `OSWorld` | [![arXiv](https://img.shields.io/badge/arXiv-2404.07972-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2404.07972)<br>OSWorld: Benchmarking Multimodal Agents for Open-Ended Tasks in Real Computer Environments | NeurIPS 2024 |
| `WebArena` | [![arXiv](https://img.shields.io/badge/arXiv-2307.13854-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2307.13854)<br>WebArena: A Realistic Web Environment for Building Autonomous Agents | ICLR 2024 |
| `CASCADE` | [![arXiv](https://img.shields.io/badge/arXiv-2512.23880-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2512.23880)<br>CASCADE: Cumulative Agentic Skill Creation through Autonomous Development and Evolution | arXiv 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2403.05175-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2403.05175)<br>Continual Learning and Catastrophic Forgetting | Learning and Memory: A Comprehensive Reference 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2510.08558-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2510.08558)<br>Agent Learning via Early Experience | ICML 2026 |


# The Six Proxy Functions

Each proxy function answers a different *question* for the agent, but all return **agent-usable feedback**.

## Dynamics Proxy

*How would the environment change if the agent executed a given action?* Video, driving, game, and model-based dynamics predictors.

| Model | Paper | Venue |
|:-:|:-|:-:|
||
| `-` | Learning Latent Dynamics for Planning from Pixels | ICML 2019 |
| `FitVid` | [![arXiv](https://img.shields.io/badge/arXiv-2106.13195-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2106.13195)<br>FitVid: Overfitting in Pixel-Level Video Prediction | arXiv 2021 |
| `VideoGPT` | [![arXiv](https://img.shields.io/badge/arXiv-2104.10157-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2104.10157)<br>VideoGPT: Video Generation using VQ-VAE and Transformers | arXiv 2021 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2204.03458-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2204.03458)<br>Video Diffusion Models | NeurIPS 2022 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2206.07696-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2206.07696)<br>Diffusion Models for Video Prediction and Infilling | TMLR 2022 |
| `MCVD` | [![arXiv](https://img.shields.io/badge/arXiv-2205.09853-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2205.09853)<br>MCVD: Masked Conditional Video Diffusion for Prediction, Generation, and Interpolation | NeurIPS 2022 |
| `GAIA-1` | [![arXiv](https://img.shields.io/badge/arXiv-2309.17080-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2309.17080)<br>GAIA-1: A Generative World Model for Autonomous Driving | arXiv 2023 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2209.00588-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2209.00588)<br>Transformers Are Sample-Efficient World Models | ICLR 2023 |
| `STORM` | STORM: Efficient Stochastic Transformer based World Models for Reinforcement Learning | NeurIPS 2023 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2405.12399-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2405.12399)<br>Diffusion for World Modeling: Visual Details Matter in Atari | NeurIPS 2024 |
| `-` | Video generation models as world simulators |  2024 |
| `Genie` | [![arXiv](https://img.shields.io/badge/arXiv-2402.15391-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2402.15391)<br>Genie: Generative Interactive Environments | ICML 2024 |
| `Vista` | [![arXiv](https://img.shields.io/badge/arXiv-2405.17398-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2405.17398)<br>Vista: A Generalizable Driving World Model with High Fidelity and Versatile Controllability | NeurIPS 2024 |
| `TD-MPC2` | [![arXiv](https://img.shields.io/badge/arXiv-2310.16828-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2310.16828)<br>TD-MPC2: Scalable, Robust World Models for Continuous Control | ICLR 2024 |
| `RoboCasa` | RoboCasa: Large-Scale Simulation of Everyday Tasks for Generalist Robots | RSS 2024 |
| `DriveDreamer` | [![arXiv](https://img.shields.io/badge/arXiv-2309.09777-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2309.09777)<br>DriveDreamer: Towards Real-World-Driven World Models for Autonomous Driving | ECCV 2024 |
| `iVideoGPT` | iVideoGPT: Interactive VideoGPTs are Scalable World Models | NeurIPS 2024 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2310.06114-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2310.06114)<br>Learning Interactive Real-World Simulators | ICLR 2024 |
| `DynamicCity` | [![arXiv](https://img.shields.io/badge/arXiv-2410.18084-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2410.18084)<br>DynamicCity: Large-Scale 4D Occupancy Generation from Dynamic Scenes | ICLR 2025 |
| `GameGen-X` | [![arXiv](https://img.shields.io/badge/arXiv-2411.00769-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2411.00769)<br>GameGen-X: Interactive Open-world Game Video Generation | ICLR 2025 |
| `-` | Genie 3: A New Frontier for World Models |  2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2510.08713-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2510.08713)<br>Towards Unified World Models for Visual Navigation via Memory-Augmented Planning and Foresight | arXiv 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2506.02918-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2506.02918)<br>World Modelling Improves Language Model Agents | arXiv 2025 |
| `MineWorld` | [![arXiv](https://img.shields.io/badge/arXiv-2504.08388-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2504.08388)<br>MineWorld: a Real-Time and Open-Source Interactive World Model on Minecraft | arXiv 2025 |
| `MobileWorldBench` | [![arXiv](https://img.shields.io/badge/arXiv-2512.14014-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2512.14014)<br>MobileWorldBench: Towards Semantic World Modeling For Mobile Agents | arXiv 2025 |
| `-` | World Model on Million-Length Video And Language With Blockwise RingAttention | ICLR 2025 |
| `Vision` | [![arXiv](https://img.shields.io/badge/arXiv-2510.16729-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2510.16729)<br>Vision-Centric 4D Occupancy Forecasting and Planning via Implicit Residual World Models | arXiv 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2506.09985-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2506.09985)<br>V-JEPA 2: Self-Supervised Video Models Enable Understanding, Prediction and Planning | arXiv 2025 |
| `-` | Diffusion Models Are Real-Time Game Engines | ICLR 2025 |
| `Marble` | Marble: A Multimodal World Model |  2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2408.14197-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2408.14197)<br>Driving in the occupancy world: Vision-centric 4d occupancy forecasting and planning via world models for autonomous driving | AAAI 2025 |
| `Matrix-Game` | [![arXiv](https://img.shields.io/badge/arXiv-2506.18701-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2506.18701)<br>Matrix-Game: Interactive World Foundation Model | arXiv 2025 |
| `Language` | [![arXiv](https://img.shields.io/badge/arXiv-2603.26741-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2603.26741)<br>Language-Conditioned World Modeling for Visual Navigation | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2601.20540-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2601.20540)<br>Advancing Open-source World Models | arXiv 2026 |
| `NavThinker` | [![arXiv](https://img.shields.io/badge/arXiv-2603.15359-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2603.15359)<br>NavThinker: Action-Conditioned World Models for Coupled Prediction and Planning in Social Navigation | arXiv 2026 |
| `LiDARCrafter` | [![arXiv](https://img.shields.io/badge/arXiv-2508.03692-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2508.03692)<br>LiDARCrafter: Dynamic 4D World Modeling from LiDAR Sequences | AAAI 2026 |
| `Self` | [![arXiv](https://img.shields.io/badge/arXiv-2604.03253-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2604.03253)<br>Self-Execution Simulation Improves Coding Models | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2605.10858-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2605.10858)<br>Is Your Driving World Model an All-Around Player? | CVPR 2026 |
| `U4D` | [![arXiv](https://img.shields.io/badge/arXiv-2512.02982-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2512.02982)<br>U4D: Uncertainty-Aware 4D World Modeling from LiDAR Sequences | CVPR 2026 |
| `AD-R1` | [![arXiv](https://img.shields.io/badge/arXiv-2511.20325-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2511.20325)<br>AD-R1: Closed-Loop Reinforcement Learning for End-to-End Autonomous Driving with Impartial World Models | CVPR 2026 |


## Spatial Proxy

*What would the agent observe from another viewpoint or position?* NeRF/Gaussian rendering, 3D/4D reconstruction and generation, and visual imagination for navigation.

| Model | Paper | Venue |
|:-:|:-|:-:|
||
| `NeRF` | [![arXiv](https://img.shields.io/badge/arXiv-2003.08934-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2003.08934)<br>NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis | ECCV 2020 |
| `Mip-NeRF` | [![arXiv](https://img.shields.io/badge/arXiv-2103.13415-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2103.13415)<br>Mip-NeRF: A Multiscale Representation for Anti-Aliasing Neural Radiance Fields | ICCV 2021 |
| `PathDreamer` | [![arXiv](https://img.shields.io/badge/arXiv-2105.08756-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2105.08756)<br>PathDreamer: A World Model for Indoor Navigation | ICCV 2021 |
| `Mip` | [![arXiv](https://img.shields.io/badge/arXiv-2111.12077-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2111.12077)<br>Mip-NeRF 360: Unbounded Anti-Aliased Neural Radiance Fields | CVPR 2022 |
| `SceneDreamer` | [![arXiv](https://img.shields.io/badge/arXiv-2302.01330-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2302.01330)<br>SceneDreamer: Unbounded 3D Scene Generation from 2D Image Collections | TPAMI 2023 |
| `SceneScape` | [![arXiv](https://img.shields.io/badge/arXiv-2302.01133-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2302.01133)<br>SceneScape: Text-Driven Consistent Scene Generation | NeurIPS 2023 |
| `Text2Room` | [![arXiv](https://img.shields.io/badge/arXiv-2303.11989-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2303.11989)<br>Text2Room: Extracting Textured 3D Meshes from 2D Text-to-Image Models | ICCV 2023 |
| `VoxPoser` | [![arXiv](https://img.shields.io/badge/arXiv-2307.05973-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2307.05973)<br>VoxPoser: Composable 3D Value Maps for Robotic Manipulation with Language Models | CoRL 2023 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2308.04079-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2308.04079)<br>3D Gaussian Splatting for Real-Time Radiance Field Rendering | TOG 2023 |
| `Nerfstudio` | [![arXiv](https://img.shields.io/badge/arXiv-2302.04264-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2302.04264)<br>Nerfstudio: A Modular Framework for Neural Radiance Field Development | SIGGRAPH Asia 2023 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2401.03890-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2401.03890)<br>A Survey on 3D Gaussian Splatting | CSUR 2024 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2402.07181-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2402.07181)<br>3D Gaussian as a New Era: A Survey | TVCG 2024 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2406.09756-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2406.09756)<br>Grounding Image Matching in 3D with MASt3R | ECCV 2024 |
| `DreamScene` | [![arXiv](https://img.shields.io/badge/arXiv-2404.03575-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2404.03575)<br>DreamScene: 3D Gaussian-based Text-to-3D Scene Generation via Formation Pattern Sampling | ECCV 2024 |
| `Scaffold-GS` | [![arXiv](https://img.shields.io/badge/arXiv-2312.00109-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2312.00109)<br>Scaffold-GS: Structured 3D Gaussians for View-Adaptive Rendering | CVPR 2024 |
| `Dreamforge` | [![arXiv](https://img.shields.io/badge/arXiv-2409.04003-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2409.04003)<br>Dreamforge: Motion-aware autoregressive video generation for multi-view driving scenes | arXiv 2024 |
| `DriveWorld` | DriveWorld: 4D Pre-trained Scene Understanding via World Models for Autonomous Driving | CVPR 2024 |
| `DimensionX` | [![arXiv](https://img.shields.io/badge/arXiv-2411.04928-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2411.04928)<br>DimensionX: Create Any 3D and 4D Scenes from a Single Image with Controllable Video Diffusion | arXiv 2024 |
| `ManiSkill3` | [![arXiv](https://img.shields.io/badge/arXiv-2410.00425-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2410.00425)<br>ManiSkill3: GPU Parallelized Robotics Simulation and Rendering for Generalizable Embodied AI | arXiv 2024 |
| `DUSt3R` | [![arXiv](https://img.shields.io/badge/arXiv-2312.14132-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2312.14132)<br>DUSt3R: Geometric 3D Vision Made Easy | CVPR 2024 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2310.08528-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2310.08528)<br>4D Gaussian Splatting for Real-Time Dynamic Scene Rendering | CVPR 2024 |
| `CityDreamer` | [![arXiv](https://img.shields.io/badge/arXiv-2309.00610-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2309.00610)<br>CityDreamer: Compositional Generative Model of Unbounded 3D Cities | CVPR 2024 |
| `Mip-Splatting` | [![arXiv](https://img.shields.io/badge/arXiv-2311.16493-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2311.16493)<br>Mip-Splatting: Alias-Free 3D Gaussian Splatting | CVPR 2024 |
| `Text2NeRF` | [![arXiv](https://img.shields.io/badge/arXiv-2305.11588-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2305.11588)<br>Text2NeRF: Text-Driven 3D Scene Generation with Neural Radiance Fields | TVCG 2024 |
| `Copilot4D` | Copilot4D: Learning Unsupervised World Models for Autonomous Driving via Discrete Diffusion | ICLR 2024 |
| `OccWorld` | [![arXiv](https://img.shields.io/badge/arXiv-2311.16038-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2311.16038)<br>OccWorld: Learning a 3D Occupancy World Model for Autonomous Driving | ECCV 2024 |
| `ReCamMaster` | [![arXiv](https://img.shields.io/badge/arXiv-2503.11647-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2503.11647)<br>ReCamMaster: Camera-Controlled Generative Rendering from A Single Video | arXiv 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2412.03572-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2412.03572)<br>Navigation world models | CVPR 2025 |
| `PhysX-Anything` | [![arXiv](https://img.shields.io/badge/arXiv-2511.13648-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2511.13648)<br>PhysX-Anything: Simulation-Ready Physical 3D Assets from Single Image | arXiv 2025 |
| `GAF` | [![arXiv](https://img.shields.io/badge/arXiv-2506.14135-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2506.14135)<br>GAF: Gaussian Action Field as a 4D Representation for Dynamic World Modeling in Robotic Manipulation | arXiv 2025 |
| `ParticleFormer` | [![arXiv](https://img.shields.io/badge/arXiv-2506.23126-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2506.23126)<br>ParticleFormer: A 3D Point Cloud World Model for Multi-Object, Multi-Material Robotic Manipulation | arXiv 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2509.07996-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2509.07996)<br>3D and 4D World Modeling: A Survey | arXiv 2025 |
| `GWM` | GWM: Towards Scalable Gaussian World Models for Robotic Manipulation | ICCV 2025 |
| `MindCube` | [![arXiv](https://img.shields.io/badge/arXiv-2506.21458-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2506.21458)<br>MindCube: Spatial Mental Modeling from Limited Views | arXiv 2025 |
| `GAIA-2` | [![arXiv](https://img.shields.io/badge/arXiv-2503.20523-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2503.20523)<br>GAIA-2: A Controllable Multi-View Generative World Model for Autonomous Driving | arXiv 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2408.16061-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2408.16061)<br>3D Reconstruction with Spatial Memory | 3DV 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2501.12387-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2501.12387)<br>Continuous 3D Perception Model with Persistent State | arXiv 2025 |
| `Fast3R` | [![arXiv](https://img.shields.io/badge/arXiv-2501.13928-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2501.13928)<br>Fast3R: Towards 3D Reconstruction of 1000+ Images in One Forward Pass | arXiv 2025 |
| `WonderWorld` | [![arXiv](https://img.shields.io/badge/arXiv-2406.09394-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2406.09394)<br>WonderWorld: Interactive 3D Scene Generation from a Single Image | CVPR 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2504.05786-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2504.05786)<br>How to Enable LLM with 3D Capacity? A Survey of Spatial Reasoning in LLM | IJCAI 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2505.05512-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2505.05512)<br>Occupancy World Model for Robots | arXiv 2025 |
| `TesserAct` | [![arXiv](https://img.shields.io/badge/arXiv-2504.20995-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2504.20995)<br>TesserAct: Learning 4D Embodied World Models | arXiv 2025 |
| `Aether` | [![arXiv](https://img.shields.io/badge/arXiv-2503.18945-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2503.18945)<br>Aether: Geometric-Aware Unified World Modeling | ICCV 2025 |
| `OccuBench` | [![arXiv](https://img.shields.io/badge/arXiv-2604.10866-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2604.10866)<br>OccuBench: Evaluating AI Agents on Real-World Professional Tasks via Language World Models | arXiv 2026 |
| `PointWorld` | [![arXiv](https://img.shields.io/badge/arXiv-2601.03782-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2601.03782)<br>PointWorld: Scaling 3D World Models for In-The-Wild Robotic Manipulation | arXiv 2026 |
| `CounterScene` | [![arXiv](https://img.shields.io/badge/arXiv-2603.21104-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2603.21104)<br>CounterScene: Counterfactual Causal Reasoning in Generative World Models for Safety-Critical Closed-Loop Evaluation | arXiv 2026 |
| `MVISTA-4D` | [![arXiv](https://img.shields.io/badge/arXiv-2602.09878-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2602.09878)<br>MVISTA-4D: View-Consistent 4D World Model with Test-Time Action Inference for Robotic Manipulation | arXiv 2026 |
| `X-scene` | [![arXiv](https://img.shields.io/badge/arXiv-2506.13558-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2506.13558)<br>X-scene: Large-scale driving scene generation with high fidelity and flexible controllability | NeurIPS 2026 |
| `Code2World` | [![arXiv](https://img.shields.io/badge/arXiv-2602.09856-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2602.09856)<br>Code2World: A GUI World Model via Renderable Code Generation | arXiv 2026 |


## Execution Proxy

*What would the digital environment return after an operation?* Web, GUI, code, shell, and API/tool execution predictors.

| Model | Paper | Venue |
|:-:|:-|:-:|
||
| `RT-2` | [![arXiv](https://img.shields.io/badge/arXiv-2307.15818-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2307.15818)<br>RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control | CoRL 2023 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2209.07753-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2209.07753)<br>Code as Policies: Language Model Programs for Embodied Control | ICRA 2023 |
| `Toolformer` | [![arXiv](https://img.shields.io/badge/arXiv-2302.04761-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2302.04761)<br>Toolformer: Language Models Can Teach Themselves to Use Tools | NeurIPS 2023 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2405.15383-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2405.15383)<br>Generating Code World Models with Large Language Models Guided by Monte Carlo Tree Search | NeurIPS 2024 |
| `AgentBench` | [![arXiv](https://img.shields.io/badge/arXiv-2308.03688-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2308.03688)<br>AgentBench: Evaluating LLMs as Agents | ICLR 2024 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2402.12275-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2402.12275)<br>WorldCoder, a Model-Based LLM Agent: Building World Models by Writing Code and Interacting with the Environment | NeurIPS 2024 |
| `Math-Shepherd` | [![arXiv](https://img.shields.io/badge/arXiv-2312.08935-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2312.08935)<br>Math-Shepherd: Verify and Reinforce LLMs Step-by-Step without Human Annotations | ACL 2024 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2410.13232-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2410.13232)<br>Web Agents with World Models: Learning and Leveraging Environment Dynamics in Web Navigation | ICLR 2025 |
| `CWM` | [![arXiv](https://img.shields.io/badge/arXiv-2510.02387-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2510.02387)<br>CWM: An Open-Weights LLM for Research on Code Generation with World Models | arXiv 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2512.23676-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2512.23676)<br>Web World Models | arXiv 2025 |
| `WebSynthesis` | [![arXiv](https://img.shields.io/badge/arXiv-2507.04370-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2507.04370)<br>WebSynthesis: World-Model-Guided MCTS for Efficient WebUI-Trajectory Synthesis | arXiv 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2411.06559-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2411.06559)<br>Is Your LLM Secretly a World Model of the Internet? Model-Based Planning for Web Agents | TMLR 2025 |
| `MegaSaM` | [![arXiv](https://img.shields.io/badge/arXiv-2412.04463-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2412.04463)<br>MegaSaM: Accurate, Fast, and Robust Structure and Motion from Casual Dynamic Videos | CVPR 2025 |
| `ToolSandbox` | [![arXiv](https://img.shields.io/badge/arXiv-2408.04682-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2408.04682)<br>ToolSandbox: A Stateful, Conversational, Interactive Evaluation Benchmark for LLM Tool Use Capabilities | NAACL 2025 |
| `ViMo` | [![arXiv](https://img.shields.io/badge/arXiv-2504.13936-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2504.13936)<br>ViMo: A Generative Visual GUI World Model for App Agents | arXiv 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2501.03575-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2501.03575)<br>Cosmos World Foundation Model Platform for Physical AI | arXiv 2025 |
| `GTM` | [![arXiv](https://img.shields.io/badge/arXiv-2512.04535-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2512.04535)<br>GTM: Simulating the World of Tools for AI Agents | arXiv 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2502.10498-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2502.10498)<br>The Role of World Models in Shaping Autonomous Driving: A Comprehensive Survey | arXiv 2025 |
| `GameFactory` | GameFactory: Creating New Games with Generative Interactive Videos | ICCV 2025 |
| `ComAct` | [![arXiv](https://img.shields.io/badge/arXiv-2606.13239-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2606.13239)<br>ComAct: Reframing Professional Software Manipulation via COM-as-Action Paradigm | arXiv 2026 |
| `MobileDreamer` | [![arXiv](https://img.shields.io/badge/arXiv-2601.04035-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2601.04035)<br>MobileDreamer: Generative Sketch World Model for GUI Agent | arXiv 2026 |
| `Computer` | [![arXiv](https://img.shields.io/badge/arXiv-2602.17365-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2602.17365)<br>Computer-Using World Model | arXiv 2026 |
| `MCP-Cosmos` | [![arXiv](https://img.shields.io/badge/arXiv-2605.09131-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2605.09131)<br>MCP-Cosmos: World Model-Augmented Agents for Complex Task Execution in MCP Environments | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2602.01576-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2602.01576)<br>Generative Visual Code Mobile World Models | arXiv 2026 |
| `IterCAD` | [![arXiv](https://img.shields.io/badge/arXiv-2606.13368-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2606.13368)<br>IterCAD: An Iterative Multimodal Agent for Visually-Grounded CAD Generation and Editing | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2602.07672-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2602.07672)<br>Debugging Code World Models | arXiv 2026 |
| `NeuralOS` | [![arXiv](https://img.shields.io/badge/arXiv-2507.08800-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2507.08800)<br>NeuralOS: Towards Simulating Operating Systems via Neural Generative Models | ICLR 2026 |
| `World-Model` | [![arXiv](https://img.shields.io/badge/arXiv-2602.15384-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2602.15384)<br>World-Model-Augmented Web Agents with Action Correction | arXiv 2026 |
| `WebWorld` | [![arXiv](https://img.shields.io/badge/arXiv-2602.14721-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2602.14721)<br>WebWorld: A Large-Scale World Model for Web Agent Training | arXiv 2026 |


## Memory, Experience & Skill Proxy

*What prior experience, constraints, or reusable skills does the agent need now?* Store-retrieve memory systems and reusable skill/behavior libraries.

| Model | Paper | Venue |
|:-:|:-|:-:|
||
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2305.14992-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2305.14992)<br>Reasoning with Language Model is Planning with World Model | EMNLP 2023 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2304.03442-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2304.03442)<br>Generative Agents: Interactive Simulacra of Human Behavior | UIST 2023 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2309.02427-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2309.02427)<br>Cognitive Architectures for Language Agents | TMLR 2024 |
| `Vismem` | [![arXiv](https://img.shields.io/badge/arXiv-2511.11007-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2511.11007)<br>Vismem: Latent vision memory unlocks potential of vision-language models | arXiv 2025 |
| `SPIRAL` | [![arXiv](https://img.shields.io/badge/arXiv-2603.08403-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2603.08403)<br>SPIRAL: Self-Evolving Action-Conditioned Video Generation via Reflective Planning Agents | arXiv 2026 |


## Reward / Verification Proxy

*Is the agent's behavior correct, safe, and feasible — and how should it improve?* Reward models, verifiers, critics, preference models, and LLM-as-judge.

| Model | Paper | Venue |
|:-:|:-|:-:|
||
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-1706.03741-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/1706.03741)<br>Deep Reinforcement Learning from Human Preferences | NeurIPS 2017 |
| `Fine` | [![arXiv](https://img.shields.io/badge/arXiv-1909.08593-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/1909.08593)<br>Fine-Tuning Language Models from Human Preferences | arXiv 2019 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2110.14168-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2110.14168)<br>Training Verifiers to Solve Math Word Problems | arXiv 2021 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2305.18290-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2305.18290)<br>Direct Preference Optimization: Your Language Model is Secretly a Reward Model | NeurIPS 2023 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2306.05685-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2306.05685)<br>Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena | NeurIPS 2023 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2310.12036-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2310.12036)<br>A General Theoretical Paradigm to Understand Learning from Human Preferences | AISTATS 2024 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2411.15594-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2411.15594)<br>A Survey on LLM-as-a-Judge | arXiv 2024 |
| `ORPO` | [![arXiv](https://img.shields.io/badge/arXiv-2403.07691-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2403.07691)<br>ORPO: Monolithic Preference Optimization without Reference Model | EMNLP 2024 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2305.20050-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2305.20050)<br>Let's Verify Step by Step | ICLR 2024 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2407.00215-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2407.00215)<br>LLM Critics Help Catch LLM Bugs | arXiv 2024 |
| `SimPO` | [![arXiv](https://img.shields.io/badge/arXiv-2405.14734-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2405.14734)<br>SimPO: Simple Preference Optimization with a Reference-Free Reward | NeurIPS 2024 |
| `WorldSimBench` | [![arXiv](https://img.shields.io/badge/arXiv-2410.18072-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2410.18072)<br>WorldSimBench: Towards Video Generation Models as World Simulators | arXiv 2024 |
| `WorldModelBench` | [![arXiv](https://img.shields.io/badge/arXiv-2502.20694-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2502.20694)<br>WorldModelBench: Judging Video Generation Models As World Models | arXiv 2025 |
| `Computer` | [![arXiv](https://img.shields.io/badge/arXiv-2511.15567-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2511.15567)<br>Computer-Use Agents as Judges for Generative User Interface | arXiv 2025 |
| `Critic-V` | [![arXiv](https://img.shields.io/badge/arXiv-2411.18203-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2411.18203)<br>Critic-V: VLM Critics Help Catch VLM Errors in Multimodal Reasoning | CVPR 2025 |


# Empowerment Levels (L1 / L2 / L3)

How proxies empower agents: <kbd>L1</kbd> inference-time guidance (advise a frozen agent), <kbd>L2</kbd> training-time optimization (generate experience/signal to train the agent), and <kbd>L3</kbd> Agent–Proxy co-evolution (both improve each other in a loop).

| Model | Paper | Venue |
|:-:|:-|:-:|
||
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2511.03773-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2511.03773)<br>Scaling Agent Learning via Experience Synthesis | arXiv 2025 |
| `RAGEN` | [![arXiv](https://img.shields.io/badge/arXiv-2504.20073-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2504.20073)<br>RAGEN: Understanding Self-Evolution in LLM Agents via Multi-Turn Reinforcement Learning | arXiv 2025 |
| `VAGEN` | [![arXiv](https://img.shields.io/badge/arXiv-2510.16907-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2510.16907)<br>VAGEN: Reinforcing World Model Reasoning for Multi-Turn VLM Agents | NeurIPS 2025 |
| `WebEvolver` | [![arXiv](https://img.shields.io/badge/arXiv-2504.21024-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2504.21024)<br>WebEvolver: Enhancing Web Agent Self-Improvement with Coevolving World Model | EMNLP 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2601.13247-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2601.13247)<br>Aligning Agentic World Models via Knowledgeable Experience Learning | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2602.10090-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2602.10090)<br>Agent World Model: Infinity Synthetic Environments for Agentic Reinforcement Learning | ICML 2026 |
| `SearchGym` | [![arXiv](https://img.shields.io/badge/arXiv-2601.14615-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2601.14615)<br>SearchGym: Bootstrapping Real-World Search Agents via Cost-Effective and High-Fidelity Environment Simulation | arXiv 2026 |


# Evaluation, Fidelity & Safety

Benchmarks and metrics for world models, fidelity and calibration limits, and the safety/attack surface of proxy-driven learning.

| Model | Paper | Venue |
|:-:|:-|:-:|
||
| `G-Eval` | [![arXiv](https://img.shields.io/badge/arXiv-2303.16634-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2303.16634)<br>G-Eval: NLG Evaluation using GPT-4 with Better Human Alignment | EMNLP 2023 |
| `Length` | [![arXiv](https://img.shields.io/badge/arXiv-2404.04475-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2404.04475)<br>Length-Controlled AlpacaEval: A Simple Way to Debias Automatic Evaluators | COLM 2024 |
| `Prometheus` | [![arXiv](https://img.shields.io/badge/arXiv-2310.08491-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2310.08491)<br>Prometheus: Inducing Fine-Grained Evaluation Capability in Language Models | ICLR 2024 |
| `BEHAVIOR-1K` | [![arXiv](https://img.shields.io/badge/arXiv-2403.09227-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2403.09227)<br>BEHAVIOR-1K: A Human-Centered, Embodied AI Benchmark with 1,000 Everyday Activities and Realistic Simulation | arXiv 2024 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2406.03689-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2406.03689)<br>Evaluating the World Model Implicit in a Generative Model | NeurIPS 2024 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2411.07690-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2411.07690)<br>World Models: The Safety Perspective | arXiv 2024 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2411.14499-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2411.14499)<br>Understanding World or Predicting Future? A Comprehensive Survey of World Models | CSUR 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2411.02385-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2411.02385)<br>How Far is Video Generation from World Model: A Physical Law Perspective | ICML 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2602.18739-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2602.18739)<br>When World Models Dream Wrong: Physical-Conditioned Adversarial Attacks against World Models | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2605.02900-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2605.02900)<br>Safety in Embodied AI: A Survey of Risks, Attacks, and Defenses | arXiv 2026 |
| `JailWAM` | [![arXiv](https://img.shields.io/badge/arXiv-2604.05498-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2604.05498)<br>JailWAM: Jailbreaking World Action Models in Robot Control | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2601.03905-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2601.03905)<br>Current Agents Fail to Leverage World Model as Tool for Foresight | arXiv 2026 |
| `CtrlAttack` | [![arXiv](https://img.shields.io/badge/arXiv-2603.13435-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2603.13435)<br>CtrlAttack: A Unified Attack on World-Model Control in Diffusion Models | arXiv 2026 |
| `SafeDream` | [![arXiv](https://img.shields.io/badge/arXiv-2604.16824-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2604.16824)<br>SafeDream: Safety World Model for Proactive Early Jailbreak Detection | arXiv 2026 |


# Surveys & Related Work

Related surveys and the paper's core position statements.

| Model | Paper | Venue |
|:-:|:-|:-:|
||
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2405.03520-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2405.03520)<br>Is Sora a World Simulator? A Comprehensive Survey on General World Models and Beyond | arXiv 2024 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2501.11260-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2501.11260)<br>A Survey of World Models for Autonomous Driving | arXiv 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2510.16732-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2510.16732)<br>A Comprehensive Survey on World Models for Embodied AI | arXiv 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2604.22748-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2604.22748)<br>Agentic World Modeling: Foundations, Capabilities, Laws, and Beyond | arXiv 2026 |


# Additional References

Further supporting works cited in the survey.

| Model | Paper | Venue |
|:-:|:-|:-:|
||
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-1707.06347-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/1707.06347)<br>Proximal Policy Optimization Algorithms | arXiv 2017 |
| `Habitat` | Habitat: A Platform for Embodied AI Research | ICCV 2019 |
| `-` | Model-Based Reinforcement Learning for Atari | ICLR 2020 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2009.01325-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2009.01325)<br>Learning to Summarize from Human Feedback | NeurIPS 2020 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2010.14406-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2010.14406)<br>Transporter Networks: Rearranging the Visual World for Robotic Manipulation | CoRL 2020 |
| `CLIPort` | [![arXiv](https://img.shields.io/badge/arXiv-2109.12098-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2109.12098)<br>CLIPort: What and Where Pathways for Robotic Manipulation | CoRL 2021 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2204.01691-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2204.01691)<br>Do As I Can, Not As I Say: Grounding Language in Robotic Affordances | CoRL 2022 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2212.08073-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2212.08073)<br>Constitutional AI: Harmlessness from AI Feedback | arXiv 2022 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2204.05862-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2204.05862)<br>Training a Helpful and Harmless Assistant with Reinforcement Learning from Human Feedback | arXiv 2022 |
| `TensoRF` | [![arXiv](https://img.shields.io/badge/arXiv-2203.09517-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2203.09517)<br>TensoRF: Tensorial Radiance Fields | ECCV 2022 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2207.05608-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2207.05608)<br>Inner Monologue: Embodied Reasoning through Planning with Language Models | CoRL 2022 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2205.11916-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2205.11916)<br>Large Language Models are Zero-Shot Reasoners | NeurIPS 2022 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2201.05989-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2201.05989)<br>Instant Neural Graphics Primitives with a Multiresolution Hash Encoding | TOG 2022 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2203.02155-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2203.02155)<br>Training Language Models to Follow Instructions with Human Feedback | NeurIPS 2022 |
| `Perceiver-Actor` | [![arXiv](https://img.shields.io/badge/arXiv-2209.05451-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2209.05451)<br>Perceiver-Actor: A Multi-Task Transformer for Robotic Manipulation | CoRL 2022 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2211.14275-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2211.14275)<br>Solving Math Word Problems with Process- and Outcome-Based Feedback | arXiv 2022 |
| `Chain-of` | [![arXiv](https://img.shields.io/badge/arXiv-2201.11903-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2201.11903)<br>Chain-of-Thought Prompting Elicits Reasoning in Large Language Models | NeurIPS 2022 |
| `Plenoxels` | [![arXiv](https://img.shields.io/badge/arXiv-2112.05131-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2112.05131)<br>Plenoxels: Radiance Fields without Neural Networks | CVPR 2022 |
| `Self` | [![arXiv](https://img.shields.io/badge/arXiv-2301.08243-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2301.08243)<br>Self-Supervised Learning from Images with a Joint-Embedding Predictive Architecture | CVPR 2023 |
| `RT-1` | [![arXiv](https://img.shields.io/badge/arXiv-2212.06817-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2212.06817)<br>RT-1: Robotics Transformer for Real-World Control at Scale | RSS 2023 |
| `Self-Refine` | [![arXiv](https://img.shields.io/badge/arXiv-2303.17651-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2303.17651)<br>Self-Refine: Iterative Refinement with Self-Feedback | NeurIPS 2023 |
| `MemGPT` | [![arXiv](https://img.shields.io/badge/arXiv-2310.08560-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2310.08560)<br>MemGPT: Towards LLMs as Operating Systems | arXiv 2023 |
| `Reflexion` | [![arXiv](https://img.shields.io/badge/arXiv-2303.11366-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2303.11366)<br>Reflexion: Language Agents with Verbal Reinforcement Learning | NeurIPS 2023 |
| `ReAct` | [![arXiv](https://img.shields.io/badge/arXiv-2210.03629-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2210.03629)<br>ReAct: Synergizing Reasoning and Acting in Language Models | ICLR 2023 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2305.10601-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2305.10601)<br>Tree of Thoughts: Deliberate Problem Solving with Large Language Models | NeurIPS 2023 |
| `RRHF` | [![arXiv](https://img.shields.io/badge/arXiv-2304.05302-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2304.05302)<br>RRHF: Rank Responses to Align Language Models with Human Feedback without Tears | NeurIPS 2023 |
| `KTO` | [![arXiv](https://img.shields.io/badge/arXiv-2402.01306-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2402.01306)<br>KTO: Model Alignment as Prospect Theoretic Optimization | ICML 2024 |
| `SWE-bench` | [![arXiv](https://img.shields.io/badge/arXiv-2310.06770-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2310.06770)<br>SWE-bench: Can Language Models Resolve Real-World GitHub Issues? | ICLR 2024 |
| `Oasis` | Oasis: A Universe in a Transformer |  2024 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2405.14205-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2405.14205)<br>Agent Planning with World Knowledge Model | NeurIPS 2024 |
| `DeepSeekMath` | [![arXiv](https://img.shields.io/badge/arXiv-2402.03300-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2402.03300)<br>DeepSeekMath: Pushing the Limits of Mathematical Reasoning in Open Language Models | arXiv 2024 |
| `VGGT` | [![arXiv](https://img.shields.io/badge/arXiv-2503.11651-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2503.11651)<br>VGGT: Visual Geometry Grounded Transformer | arXiv 2025 |
| `MonST3R` | [![arXiv](https://img.shields.io/badge/arXiv-2410.03825-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2410.03825)<br>MonST3R: A Simple Approach for Estimating Geometry in the Presence of Motion | ICLR 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2604.02029-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2604.02029)<br>The latent space: Foundation, evolution, mechanism, ability, and outlook | arXiv 2026 |


# Acknowledgements

This list is maintained alongside the survey. Thanks to all contributors and to the authors of the works listed here.
