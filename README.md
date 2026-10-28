[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome) [![PR's Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat)](https://github.com/worldbench/awesome-agentic-world-model/pulls) ![Visitors](https://visitor-badge.laobi.icu/badge?page_id=worldbench.awesome-agentic-world-model&left_color=gray&right_color=blue) [![arXiv](https://img.shields.io/badge/arXiv-2608.02713-b31b1b?style=flat&logo=arxiv)](https://arxiv.org/abs/2608.02713) [![Hugging Face Papers](https://img.shields.io/badge/Hugging%20Face-Papers-ffcc4d?style=flat&logo=huggingface)](https://huggingface.co/papers/2608.02713)

# Awesome Agentic World Modeling

This repository accompanies the position paper **"Quo Vadis, World Modeling? Towards Interactive World Proxies for Continually Improving Agents,"** and curates the works it reviews. The survey argues for a shift from a **World Model** that passively predicts the next physical state toward an **Agent-Centric World Proxy**: an environment-grounded interface that returns the *information transition* an agent needs (a future state, rendered view, execution result, retrieved memory or skill, or verdict on a plan) to plan, learn, and continually improve.

The taxonomy has two orthogonal axes:

- **Six proxy functions** (*what* feedback the proxy returns): **Dynamics**, **Spatial**, **Execution**, **Memory / Experience**, **Skill**, and **Reward / Verification**.
- **Three empowerment levels** (*how* the proxy improves the agent): <kbd>L1</kbd> inference-time guidance, <kbd>L2</kbd> training-time optimization, and <kbd>L3</kbd> Agent-Proxy co-evolution.

## Call for Contributions

Agentic world modeling moves fast, and the boundary between a passive *world model* and an agent-facing *world proxy* is still being drawn. This list aims to be a living, community-maintained map of that space, and contributions of new work or corrections are very welcome.

To contribute, open an issue or a pull request:

- **Where:** add each entry to the section matching its proxy function (or the closest one), and keep every table in chronological order.
- **Format:** follow the existing row layout: a short model name in `Model` (or `-` if none), the title with an arXiv badge in `Paper`, and the abbreviated venue with year in `Venue`.
- **Verify:** check the title, authors, arXiv ID, and venue against the primary source before adding, and prefer the formally published version whenever one exists.
- **Fix:** corrections to venues, broken links, or mis-categorized entries are equally welcome; flag them in an issue or fix them directly in a pull request.

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
- [Citation](#citation)


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

Why real-environment interaction alone cannot carry continual improvement: cost, safety, latency, and the need for scalable feedback.

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
| `SPIRAL` | [![arXiv](https://img.shields.io/badge/arXiv-2603.08403-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2603.08403)<br>SPIRAL: Self-Evolving Action-Conditioned Video Generation via Reflective Planning Agents | arXiv 2026 |
| `FlowWAM` | [![arXiv](https://img.shields.io/badge/arXiv-2607.13017-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.13017)<br>FlowWAM: Optical Flow as a Unified Action Representation for World Action Models | arXiv 2026 |
| `LeapBot` | [![arXiv](https://img.shields.io/badge/arXiv-2607.23969-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.23969)<br>LeapBot-WA: World-Anchor Action Models via Predictive Latent Alignments | arXiv 2026 |
| `Enfold` | [![arXiv](https://img.shields.io/badge/arXiv-2607.26657-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.26657)<br>Enfold: Folding World Model Imagination into Predictive Representations for Ultra-Efficient Embodied Control | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2607.27599-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.27599)<br>World Action Planner: Generalizable Decision-Making with Action-Conditioned World Models | arXiv 2026 |
| `Auto` | [![arXiv](https://img.shields.io/badge/arXiv-2607.29031-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.29031)<br>Auto-JEPA: A Latent World Model of Continuous Intent for End-to-End Autonomous Driving | arXiv 2026 |
| `Faster` | [![arXiv](https://img.shields.io/badge/arXiv-2608.02365-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.02365)<br>Faster-WAM: Do World Action Models Need Deep Action Modules? | arXiv 2026 |
| `DF$^3$` | [![arXiv](https://img.shields.io/badge/arXiv-2608.02428-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.02428)<br>DF$^3$: World Modeling via Decoder-Free Feature Forecasting in Autonomous Navigation | arXiv 2026 |
| `SG` | [![arXiv](https://img.shields.io/badge/arXiv-2608.01397-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.01397)<br>SG-WAM: Self-Guided World Modeling in Geometry-Aware Policy Space | arXiv 2026 |
| `LAWM` | [![arXiv](https://img.shields.io/badge/arXiv-2608.05706-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.05706)<br>LAWM-3D: Learning 3D-Aware Latent Actions from Human Videos for Generalizable Robot World Models | arXiv 2026 |
| `XEWorld` | [![arXiv](https://img.shields.io/badge/arXiv-2608.05799-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.05799)<br>XEWorld: Can Action-Conditioned World Models Generalize to Unseen Robot Embodiments? | arXiv 2026 |
| `Adaptive` | [![arXiv](https://img.shields.io/badge/arXiv-2608.06008-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.06008)<br>Adaptive-WAM: Quality-Guided Early-Exit Planning from Intermediate Video-Diffusion Features | arXiv 2026 |
| `GWM` | [![arXiv](https://img.shields.io/badge/arXiv-2608.07619-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.07619)<br>GWM-VLA: Geometry-Aware Latent World Modeling for Vision-Language-Action Learning | arXiv 2026 |
| `4D` | [![arXiv](https://img.shields.io/badge/arXiv-2608.08023-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.08023)<br>4D-WAM: Infusing Spatiotemporal Awareness into World Action Models through Trajectory Fields | arXiv 2026 |
| `WA` | [![arXiv](https://img.shields.io/badge/arXiv-2608.08725-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.08725)<br>WA-SpecDec: World-Aware Speculative Decoding for Vision-Language-Action Models | arXiv 2026 |
| `JEPA` | [![arXiv](https://img.shields.io/badge/arXiv-2608.09381-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.09381)<br>JEPA-WAM: Learning Vision-Language-Action Policies with Joint-Embedding World Modeling | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.09730-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.09730)<br>World Tokens: Enhancing Embodied Policies with Training-Time World Modeling | arXiv 2026 |
| `SLIM` | [![arXiv](https://img.shields.io/badge/arXiv-2608.09771-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.09771)<br>SLIM-0.5B: Learning Action-Grounded Predictive Latents for Robot Manipulation | arXiv 2026 |
| `Energy` | [![arXiv](https://img.shields.io/badge/arXiv-2608.09876-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.09876)<br>Energy-Structured Latent World Models with Neural Time Fields for Physically Constistent Open-World Motion Planning | arXiv 2026 |
| `Dreamer` | [![arXiv](https://img.shields.io/badge/arXiv-2608.10386-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.10386)<br>Dreamer-SAC: Off-Policy Learning in Latent World Models for Sample-Efficient Autonomous Driving | arXiv 2026 |
| `BrainWAM` | [![arXiv](https://img.shields.io/badge/arXiv-2608.12854-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.12854)<br>BrainWAM: Action-Space Coordination of Semantic Priors and Predictive Dynamics for Autonomous Driving | arXiv 2026 |
| `DreamX` | [![arXiv](https://img.shields.io/badge/arXiv-2608.13489-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.13489)<br>DreamX-Phi 1.0: Action-Conditioned Video World Model for Robotic Manipulation | arXiv 2026 |
| `ForgeWM` | [![arXiv](https://img.shields.io/badge/arXiv-2608.14022-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.14022)<br>ForgeWM: Progressive Causal Training for Few-Step Action-Conditioned Video World Models | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.17163-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.17163)<br>Q-Learning With World Models | arXiv 2026 |
| `Hydra` | [![arXiv](https://img.shields.io/badge/arXiv-2608.18077-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.18077)<br>Hydra-0: Action Flow for Generalist World Modeling and Control | arXiv 2026 |
| `GigaBrain` | [![arXiv](https://img.shields.io/badge/arXiv-2608.18234-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.18234)<br>GigaBrain-WBC-0.5: A Behavior World Model for Robust Whole-Body Control with Environment Interaction | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.18669-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.18669)<br>Reinforced Planning with Latent World Models | arXiv 2026 |
| `DA` | [![arXiv](https://img.shields.io/badge/arXiv-2608.19085-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.19085)<br>DA-WAM: Decision-Aligned Future Latents for Driving World Models | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2607.26924-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.26924)<br>Temporally Centered SIGReg Improves Multi-Task LeWorldModel Learning: From Analysis to Method | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.04653-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.04653)<br>Overcoming Statistical Bias in Action-Controllable World Models | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2607.27036-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.27036)<br>Mitigating Compounding Error via Video Representation Regularization | arXiv 2026 |
| `ODEWorld` | [![arXiv](https://img.shields.io/badge/arXiv-2607.27924-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.27924)<br>ODEWorld: A Continuous Predictive Architecture via Physical-Time Flow | arXiv 2026 |
| `GeniWorld` | [![arXiv](https://img.shields.io/badge/arXiv-2608.06332-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.06332)<br>GeniWorld: A Generalizable Interactive World Model for Robotic Manipulation via Visual Actions | arXiv 2026 |
| `ContactFlow` | [![arXiv](https://img.shields.io/badge/arXiv-2607.26579-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.26579)<br>ContactFlow: A video action conditioning that transfers across embodiments | arXiv 2026 |
| `EmbodiedVAE` | [![arXiv](https://img.shields.io/badge/arXiv-2608.02990-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.02990)<br>EmbodiedVAE: Disentangled Video VAE for Efficient and Controllable Embodied Manipulation | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.16885-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.16885)<br>$τ_0$-VLA: a Hierarchical Robot Foundation Model with World-Model-Guided Test-Time Computation | arXiv 2026 |
| `Depth` | [![arXiv](https://img.shields.io/badge/arXiv-2607.16314-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.16314)<br>Depth-Regularized JEPA World Models Learn More Transferable Representations from Real Outdoor Robot Data | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.06799-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.06799)<br>Is Forward Prediction Enough? Physical State Grounding for JEPA World Models | arXiv 2026 |
| `Xiaomi` | [![arXiv](https://img.shields.io/badge/arXiv-2607.11643-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.11643)<br>Xiaomi-Robotics-U0: Unified Embodied Synthesis with World Foundation Model | arXiv 2026 |
| `MiniWorld` | [![arXiv](https://img.shields.io/badge/arXiv-2608.01127-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.01127)<br>MiniWorld: Democratizing the Training of Video World Models from Scratch | arXiv 2026 |
| `BWM` | [![arXiv](https://img.shields.io/badge/arXiv-2607.29302-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.29302)<br>BWM: A Low-Cost High-Fidelity World Simulator for Robot Learning | arXiv 2026 |
| `S2` | [![arXiv](https://img.shields.io/badge/arXiv-2608.13103-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.13103)<br>S2-HWM: Sparse Event-Structured Hierarchical World Model for Long-Horizon Surgical Robot Manipulation | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2607.21594-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.21594)<br>Streaming Multi-Agent Autoregressive Diffusion Model with World State Registers | arXiv 2026 |
| `Population` | [![arXiv](https://img.shields.io/badge/arXiv-2608.08600-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.08600)<br>Population-Scalable Multi-Agent World Modeling | arXiv 2026 |
| `DreamQAS` | [![arXiv](https://img.shields.io/badge/arXiv-2607.29491-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.29491)<br>DreamQAS: Learning a Decision-Useful World Model for VQE-Efficient Quantum Architecture Search | arXiv 2026 |
| `FedWorld` | [![arXiv](https://img.shields.io/badge/arXiv-2608.01561-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.01561)<br>FedWorld: Scope-Aware Federation of Agent World Models | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.17739-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.17739)<br>Offline Multi-Agent Reinforcement Learning with a Physics-Informed World Model for Cooperative Mixed Traffic Control | arXiv 2026 |
| `DreamTrajectory` | [![arXiv](https://img.shields.io/badge/arXiv-2608.01381-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.01381)<br>DreamTrajectory: Trajectory-Guided Action Generation with World Model Alignment for Mobile Manipulation | arXiv 2026 |
| `EndoWAM` | [![arXiv](https://img.shields.io/badge/arXiv-2608.01221-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.01221)<br>EndoWAM: A Grounded World-Action Model for Generalizable Endoscopic Navigation | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.11204-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.11204)<br>Surgical WAM: A World-Action Model for Data-Efficient Surgical Robot Learning | arXiv 2026 |
| `Motus2` | [![arXiv](https://img.shields.io/badge/arXiv-2608.30237-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.30237)<br>Motus2: A Self-Evolving General World Model for Dexterous Manipulation | arXiv 2026 |
| `LeWM+I` | [![arXiv](https://img.shields.io/badge/arXiv-2610.03137-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.03137)<br>Keeping JEPA World Models Plannable When Little of the Frame Moves | arXiv 2026 |
| `SufficientPlan` | [![arXiv](https://img.shields.io/badge/arXiv-2610.08350-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.08350)<br>How Much Planning Is Enough? Reducing Search and Computation in World-Model Planning | arXiv 2026 |
| `UNITAS` | [![arXiv](https://img.shields.io/badge/arXiv-2610.12099-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.12099)<br>UNITAS: A 3D-Native World Action Model for Embodied Manipulation | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2610.19579-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.19579)<br>Back on Track: Deployment-time Policy Improvement via World Model Planning | arXiv 2026 |
| `VQ-WM` | [![arXiv](https://img.shields.io/badge/arXiv-2610.25600-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.25600)<br>Vector-Quantized World Model: Latent Feedback Motion Planning for Robot Manipulation | arXiv 2026 |
| `ActTime` | [![arXiv](https://img.shields.io/badge/arXiv-2610.25764-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.25764)<br>ActTime: Action-Conditioned World Modeling for Time Series | arXiv 2026 |
| `EmbodiedWorld-200K` | [![arXiv](https://img.shields.io/badge/arXiv-2610.25959-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.25959)<br>EmbodiedWorld-200K: Toward Embodied World Agents via Embodied-Planning Dataset and Interactive World Models · [Project](https://xiaokunfeng.github.io/EmbodiedWorld-200K/) | arXiv 2026 |
| `Ropedia W0` | [![arXiv](https://img.shields.io/badge/arXiv-2610.26855-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.26855)<br>Ropedia W0: Scaling Loco-Manipulation World Models across Embodiments with Human Experience · [Project](https://ropedia.github.io/ropedia-w0/) | arXiv 2026 |
| `DRILL` | [![arXiv](https://img.shields.io/badge/arXiv-2610.30814-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.30814)<br>DRILL: Training World Models to Improve Policies, Not Predict Pixels | arXiv 2026 |


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
| `UniNav` | [![arXiv](https://img.shields.io/badge/arXiv-2608.03244-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.03244)<br>UniNav: A Unified World-Action Diffusion Model for Visual Navigation | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.07548-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.07548)<br>SC$^{2}$-WM: A Self-Correcting World Model with Closed-Loop Feedback for Vision-and-Language Navigation in Continuous Environments | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.09073-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.09073)<br>Latent World Models with Monotone Planning Costs for Image-Goal Navigation | arXiv 2026 |
| `Orbit` | [![arXiv](https://img.shields.io/badge/arXiv-2608.16651-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.16651)<br>Orbit-Planner: Towards Latent World Models for On-Orbit Obstacle Avoidance of Satellite Agents | arXiv 2026 |
| `World` | [![arXiv](https://img.shields.io/badge/arXiv-2608.19661-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.19661)<br>World-Model-Grounded LLM Planning for AUV and ASV Navigation Near Offshore Wind Farms | arXiv 2026 |
| `D-JEPA` | [![arXiv](https://img.shields.io/badge/arXiv-2609.24749-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2609.24749)<br>D-JEPA: A Decision-Aligned Latent World Model · [Code](https://github.com/NEBULIS-Lab/D-JEPA) · [Project](https://nebulis-lab.com/D-JEPA/) | arXiv 2026 |
| `InJePA` | [![arXiv](https://img.shields.io/badge/arXiv-2610.23896-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.23896)<br>InJePA: Intention-First Latent Planning with Coupled JEPA World Models for Visual Navigation · [Code and checkpoint](https://github.com/zhuxun132/InJepa)<br><kbd>L1</kbd> Goal-conditioned latent intentions guide stepwise action inference; predicted consequences feed the next intention and action within each candidate. | arXiv 2026 |
| `WorldMirror` | [![arXiv](https://img.shields.io/badge/arXiv-2610.31834-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.31834)<br>WorldMirror: Agentic Real-to-Sim Generation of Interactive Worlds from In-the-Wild Robot Demonstrations | arXiv 2026 |


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
| `WorldEvolver` | [![arXiv](https://img.shields.io/badge/arXiv-2606.30639-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2606.30639)<br>Self-Evolving World Models for LLM Agent Planning | arXiv 2026 |
| `AppDeltaWorld` | [![arXiv](https://img.shields.io/badge/arXiv-2608.05891-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.05891)<br>AppDeltaWorld: Transition-Grounded Delta Code World Model for Mobile GUI Agents | arXiv 2026 |
| `WebRider` | [![arXiv](https://img.shields.io/badge/arXiv-2608.06704-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.06704)<br>WebRider: Persona-Conditioned Intent Controllers for Live-Web Assistance | arXiv 2026 |
| `Twin` | [![arXiv](https://img.shields.io/badge/arXiv-2608.14490-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.14490)<br>Twin: Playing an Unknown Game with a Test-Time Digital Twin | arXiv 2026 |
| `WM-R1` | [![arXiv](https://img.shields.io/badge/arXiv-2608.27508-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.27508)<br>WM-R1: Training GUI Agents to Reason and leverage World Models with Reinforcement Learning | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2609.02885-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2609.02885)<br>Discriminative World Models for Web Agents | arXiv 2026 |
| `EvoBelief` | [![arXiv](https://img.shields.io/badge/arXiv-2610.12789-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.12789)<br>EvoBelief: Falsifiable World Models for Self-Improving LLM Agents | arXiv 2026 |
| `CoworkEnv` | [![arXiv](https://img.shields.io/badge/arXiv-2610.24960-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.24960)<br>CoworkEnv: Synthesizing Training Environments for Long-Horizon Cowork Agents · [Code](https://github.com/HKUST-KnowComp/CoworkEnv) | arXiv 2026 |
| `WildAWM` | [![arXiv](https://img.shields.io/badge/arXiv-2610.26828-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.26828)<br>Agent World Model in the Wild: Computer-Use Agent Environment Synthesis · [Code](https://github.com/MSR-Orchard/WildAWM) | arXiv 2026 |
| `Trace2World` | [![arXiv](https://img.shields.io/badge/arXiv-2610.30792-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.30792)<br>Trace2World: Reconstructing App Worlds from Real Interaction Traces for Scalable GUI Agent Training | arXiv 2026 |
| `MIMESIS` | [![arXiv](https://img.shields.io/badge/arXiv-2610.09484-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.09484)<br>MIMESIS: Learning User Simulators as Training Environments for Interactive Agents · [Project](https://viethoang1512.github.io/mimesis/) · [Code](https://github.com/VietHoang1512/mimesis) · [Models](https://huggingface.co/collections/phanviethoang1512/mimesis)<br><kbd>L2</kbd> Frozen user simulator for multi-turn agent RL; CSD provides training-only supervision. | arXiv 2026 |


## Memory, Experience & Skill Proxy

*What prior experience, constraints, or reusable skills does the agent need now?* Store-retrieve memory systems and reusable skill/behavior libraries.

| Model | Paper | Venue |
|:-:|:-|:-:|
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.22215-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.22215)<br>Dual-Layer Agentic Memory with Fast Write Routing and Slow Consolidation | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.22767-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.22767)<br>The Retriever Should Remember: Experience-Amortized Reranking for Long-Term Agent Memory | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.21690-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.21690)<br>Context as an Environment: Programmatic Context Management for Long-Horizon Agents | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.28476-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.28476)<br>ContextPilot: Teaching Agents for Proactive Context Management via Fine-grained RL | EMNLP 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.18704-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.18704)<br>MemFuse: Multi-Source Memory Fusion from Fragmented Observations | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.24876-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.24876)<br>Recursive Experiential-Working Memory Evolution for Long-Horizon Agent Harnesses | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.22793-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.22793)<br>TRACE: A Self-Evolving Skill Bank for Consistent, Limit-Aware LLM Agents | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.25500-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.25500)<br>CaSKG: Counterfactual-Causal Skill Graphs for Scalable Agent Skill Retrieval | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.22610-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.22610)<br>Coalition-Aware Skill Reliability for Self-Evolving Agents | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.22339-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.22339)<br>When Not to Imitate: Boundary-Aware Skill Memory for Reliable Tool-Use LLM Agents | EMNLP 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.20274-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.20274)<br>Break It Down, Pass It On: Cross-Task Skill Transfer in LLM Agents | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.27454-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.27454)<br>WikiSkill: Compiling Agent Experience into Persistent Knowledge for Skill Evolution | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.25091-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.25091)<br>Auto-Policy, not Auto-Skill: Compiled Agent Skills for the Physical World | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.24747-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.24747)<br>SkillForge: Evolving Verifiable Skills for Reinforcement Learning Agents | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.25776-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.25776)<br>EVOMAL: Self-Poisoning in Self-Evolving Coding Agents | arXiv 2026 |
||
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2305.14992-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2305.14992)<br>Reasoning with Language Model is Planning with World Model | EMNLP 2023 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2304.03442-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2304.03442)<br>Generative Agents: Interactive Simulacra of Human Behavior | UIST 2023 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2309.02427-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2309.02427)<br>Cognitive Architectures for Language Agents | TMLR 2024 |
| `Vismem` | [![arXiv](https://img.shields.io/badge/arXiv-2511.11007-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2511.11007)<br>Vismem: Latent vision memory unlocks potential of vision-language models | arXiv 2025 |
| `MemHarness` | [![arXiv](https://img.shields.io/badge/arXiv-2607.28272-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.28272)<br>MemHarness: Memory Is Reconstructed, Not Replayed | arXiv 2026 |
| `MemWM` | [![arXiv](https://img.shields.io/badge/arXiv-2608.07107-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.07107)<br>MemWM: Memory-Augmented Text-Based World Model | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.05784-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.05784)<br>Activity Frames: Deterministic Screen-Activity Compilation for Agent Memory and Replay | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.12476-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.12476)<br>Governed Persistent Memory: Source-Bound State Semantics and Fail-Closed Release for Long-Horizon Agents | arXiv 2026 |
| `PBD` | [![arXiv](https://img.shields.io/badge/arXiv-2608.10449-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.10449)<br>PBD-AG: Persistent Baseline-Delta Active Graphs with Uncertainty-Aware Inspection for Long-Horizon Service Robots | arXiv 2026 |
| `LUCID` | [![arXiv](https://img.shields.io/badge/arXiv-2608.07746-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.07746)<br>LUCID: Latent-Skill Unified Control via Imagined Dynamics for Long-Horizon Humanoid Loco-Manipulation | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.09168-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.09168)<br>From Relevance to Execution Utility: Reward-Aware Dynamic Execution Gating for Skill-Based LLM Agents | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.18647-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.18647)<br>Progressive Experience Fusion for Multi-Task World Model Control in Endovascular Navigation | arXiv 2026 |
| `PoS` | [![arXiv](https://img.shields.io/badge/arXiv-2610.01415-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.01415)<br>Beyond Memory: Harnessing Long-Horizon Agents with Explicit Belief States · [Code](https://github.com/luoyu100/PoS) · [Project](https://luoyu100.github.io/projects/progression-of-states/project/) | arXiv 2026 |
| `MemoWM` | [![arXiv](https://img.shields.io/badge/arXiv-2610.10778-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.10778)<br>MemoWM: How World Models Change What Agents Need to Remember · [Code](https://github.com/Feld-maxiu/MemoWM) | arXiv 2026 |
| `ViSkill` | [![arXiv](https://img.shields.io/badge/arXiv-2610.12403-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.12403)<br>ViSkill: Reinforcing VLM Agents with Evolving Visual-Native Skills · [Code](https://github.com/ZJU-REAL/ViSkill) | arXiv 2026 |
| `TallyMem` | [![arXiv](https://img.shields.io/badge/arXiv-2610.19474-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.19474)<br>Beyond Retrieval: Evidence Access and Event Aggregation in Agent Memory | arXiv 2026 |
| `MemComposer` | [![arXiv](https://img.shields.io/badge/arXiv-2610.21091-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.21091)<br>MemComposer: Learning to Assemble Memories for LLM Agents via Reinforcement Learning | arXiv 2026 |
| `AiO-Mem` | [![arXiv](https://img.shields.io/badge/arXiv-2610.21147-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.21147)<br>All-in-One Memory: Process-Rewarded Reinforcement Learning for Memory Agents | arXiv 2026 |
| `MemScope` | [![arXiv](https://img.shields.io/badge/arXiv-2610.21170-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.21170)<br>MemScope: Evolving Agent Memory Architectures through Localized Code Repair | arXiv 2026 |
| `TrackRL` | [![arXiv](https://img.shields.io/badge/arXiv-2610.25126-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.25126)<br>Trackable Skill Library Lifecycle Management for Agentic Reinforcement Learning | arXiv 2026 |


## Reward / Verification Proxy

*Is the agent's behavior correct, safe, and feasible, and how should it improve?* Reward models, verifiers, critics, preference models, and LLM-as-judge.

| Model | Paper | Venue |
|:-:|:-|:-:|
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.27487-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.27487)<br>Grounded Checklist Partial Credit for Agent Skill Trajectories | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.28128-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.28128)<br>VICT: Verifier-Instrumented Credit Tracing for Long-Horizon LLM Agent Reinforcement Learning | EMNLP 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.29605-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.29605)<br>Hindsight Memory-PRM: Supervising Memory Management with Auditable Hindsight Credit | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.23493-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.23493)<br>SRPO: Self-Reflective Policy Optimization for Long-Horizon Reasoning | ICML 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.18719-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.18719)<br>Competence, Not Accuracy: A Diagnostic for Reference-Free Judge Gates in Skill Optimization | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.24087-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.24087)<br>Knowing When to Ask for Help: Bayesian Self-Escalation in Hierarchical LLM Agents | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.25553-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.25553)<br>When Stale Constraints Go Unchecked: Budgeted Verification Failures in Inherited Agent Memory | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.21867-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.21867)<br>MemGuard: Persisting Verifier Signals for LLM-Agent Memory Governance | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.19197-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.19197)<br>SPADE: Self-Play in Adaptive Synthetic Executable Environments | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.19880-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.19880)<br>EnvHarness: Awakening Static Worlds for Agent Learning | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.23200-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.23200)<br>LongWoF-Bench: Evaluating EvoMap Genes for Verifiable Long-Workflow Tasks | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.22421-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.22421)<br>Where World Models Break: Natural-Input Failure Discovery | arXiv 2026 |
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
| `WCM` | [![arXiv](https://img.shields.io/badge/arXiv-2607.29613-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.29613)<br>WCM: A World Critic Model for Vision-Language-Action Reinforcement Learning | arXiv 2026 |
| `CheckVLA` | [![arXiv](https://img.shields.io/badge/arXiv-2607.26789-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.26789)<br>CheckVLA: Execution-Time Verification with Action-Conditioned World Model for Long-Horizon Mobile Manipulation | arXiv 2026 |
| `ContactGuard` | [![arXiv](https://img.shields.io/badge/arXiv-2608.13438-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.13438)<br>ContactGuard: Pre-Contact Execution Monitoring with Action-Conditioned Latent World Models | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2607.27511-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.27511)<br>Failure Detection for Surgical Robot Imitation Policies via Flow-Matching World Modeling | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.17496-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.17496)<br>Calibrated Predictive Safety for Heterogeneous Robots: An Action-Conditioned JEPA Framework with Model-Based Safety Shields | arXiv 2026 |
| `Ontology` | [![arXiv](https://img.shields.io/badge/arXiv-2608.13901-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.13901)<br>Ontology-Grounded World Models for Failure Diagnosis and Closed-Loop Repair in Physical AI Systems | arXiv 2026 |
| `StructReward` | [![arXiv](https://img.shields.io/badge/arXiv-2608.08326-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.08326)<br>StructReward: Efficient Structured Process Rewards for Self-Correcting Multimodal Reasoning | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.07280-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.07280)<br>Why Study Emergent Behavior When You Can Regulate It? Aligning Multi-Agent Systems with Reward Prediction | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.05643-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.05643)<br>Refining Over Resampling: Test-Time Self-Correction for LLM Reasoning | arXiv 2026 |
| `ARC` | [![arXiv](https://img.shields.io/badge/arXiv-2608.13622-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.13622)<br>ARC: Fair Relative Advantage Comparison in Open-Ended Real-World Interaction | arXiv 2026 |
| `LGWM` | [![arXiv](https://img.shields.io/badge/arXiv-2610.11942-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.11942)<br>Right Screen, Wrong Transition: World Models as Verifiers for GUI Agents | arXiv 2026 |
| `VeriVLA` | [![arXiv](https://img.shields.io/badge/arXiv-2610.21985-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.21985)<br>VeriVLA: Adaptive Test-Time Verification for Flow-Based VLAs with Latent World Models | arXiv 2026 |


# Empowerment Levels (L1 / L2 / L3)

How proxies empower agents: <kbd>L1</kbd> inference-time guidance (advise a frozen agent), <kbd>L2</kbd> training-time optimization (generate experience/signal to train the agent), and <kbd>L3</kbd> Agent-Proxy co-evolution (both improve each other in a loop).

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
| `hint$^2$` | [![arXiv](https://img.shields.io/badge/arXiv-2608.13678-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.13678)<br>hint$^2$: Hierarchical World Models for Inference-Time Temporal Logic Guidance | arXiv 2026 |


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
| `KineBench` | [![arXiv](https://img.shields.io/badge/arXiv-2607.19876-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.19876)<br>KineBench: Benchmarking Embodied World Models via IDM-Free Kinematic Grounding | arXiv 2026 |
| `Apple` | [![arXiv](https://img.shields.io/badge/arXiv-2607.16401-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.16401)<br>Apple-$π$: Benchmarking Thinking with Video Towards Law-Grounded Physical Intelligence | arXiv 2026 |
| `WorldExam` | [![arXiv](https://img.shields.io/badge/arXiv-2608.02603-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.02603)<br>WorldExam: Benchmarking World Models from Apparent Appearance to Inherent Reactivity | arXiv 2026 |
| `GAUGE` | [![arXiv](https://img.shields.io/badge/arXiv-2608.05948-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.05948)<br>GAUGE: A Measurement-Grounded Benchmark for Physical Fidelity in Simulation Engines and Video World Models | arXiv 2026 |
| `H2R` | [![arXiv](https://img.shields.io/badge/arXiv-2608.13049-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.13049)<br>H2R-Bench: Benchmarking Human-to-Robot Manipulation Video Generation in World Models | arXiv 2026 |
| `WorldSimProbe` | [![arXiv](https://img.shields.io/badge/arXiv-2608.09298-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.09298)<br>WorldSimProbe: Diagnosing Simulator Faithfulness in Action-Conditioned World Models for Embodied Manipulation | arXiv 2026 |
| `VIScore` | [![arXiv](https://img.shields.io/badge/arXiv-2608.11174-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.11174)<br>VIScore: Diagnosing Planning-Relevant Quality in Latent World Models | arXiv 2026 |
| `HarnessEval` | [![arXiv](https://img.shields.io/badge/arXiv-2608.16859-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.16859)<br>HarnessEval-W: Agentifying the Evaluation of Visual Worlds | arXiv 2026 |
| `CG` | [![arXiv](https://img.shields.io/badge/arXiv-2607.26452-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.26452)<br>CG-World: A Large-Scale World-State Dataset and Protocol for World Models | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2607.27017-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.27017)<br>What Can Latent World Models Know? Physical Parameter Identifiability in Multimodal Predictive Representations | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.14481-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.14481)<br>Ensuring Safe Physical AI in Urban Mobility via Hazard-Informed Synthesized Envelopes | arXiv 2026 |
| `StateAliasBench` | [![arXiv](https://img.shields.io/badge/arXiv-2609.32679-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2609.32679)<br>The GUI Is Not the State: Diagnosing State Aliasing in GUI World Models | arXiv 2026 |
| `GlobeBench` | [![arXiv](https://img.shields.io/badge/arXiv-2610.22708-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.22708)<br>GlobeBench: Evaluating Text-Based World Model Capabilities for Scalable Environment Simulations · [Code](https://github.com/patronus-ai/globebench) | arXiv 2026 |
| `AnyGoal` | [![arXiv](https://img.shields.io/badge/arXiv-2610.26844-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2610.26844)<br>AnyGoal: On World Model Generalization Beyond Expert Rollouts · [Code](https://github.com/galilai-group/AnyGoal) · [Project](https://hazel-heejeong-nam.github.io/anygoal/) | arXiv 2026 |


# Surveys & Related Work

Related surveys and the paper's core position statements.

| Model | Paper | Venue |
|:-:|:-|:-:|
||
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.29596-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.29596)<br>A Systematic Survey of Agentic Skills: Architecture, Lifecycle, and Security | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2405.03520-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2405.03520)<br>Is Sora a World Simulator? A Comprehensive Survey on General World Models and Beyond | arXiv 2024 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2501.11260-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2501.11260)<br>A Survey of World Models for Autonomous Driving | arXiv 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2510.16732-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2510.16732)<br>A Comprehensive Survey on World Models for Embodied AI | arXiv 2025 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2604.22748-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2604.22748)<br>Agentic World Modeling: Foundations, Capabilities, Laws, and Beyond | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2607.17560-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2607.17560)<br>Reinforcement Learning: From Algorithms To Foundation Models | arXiv 2026 |
| `Planning` | [![arXiv](https://img.shields.io/badge/arXiv-2608.20111-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.20111)<br>Planning-Oriented End-to-End Autonomous Driving: Architectures, Evaluation, and Emerging Paradigms | arXiv 2026 |
| `-` | [![arXiv](https://img.shields.io/badge/arXiv-2608.10618-b31b1b?style=flat-square&logo=arxiv)](https://arxiv.org/abs/2608.10618)<br>Toward the Cognitive--Physical Limits of Embodied Intelligence through a World-Model-Centric Autonomous Racing Agent | arXiv 2026 |


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


# Citation

If you find this work useful, please consider citing:

```bibtex
@article{yang2026worldproxy,
  title   = {Quo Vadis, World Modeling?},
  author  = {Yu Yang and Xuemeng Yang and Licheng Wen and Lingdong Kong and Xiaobin Hu and Dongyue Lu and Wei Chow and Xiyan Huang and Yuxiang Feng and Yue Liao and Jianbiao Mei and Daocheng Fu and Rong Wu and Pinlong Cai and Ran Yi and Ying Tai and Jiangning Zhang and Botian Shi and Yong Liu and Shuicheng Yan},
  journal = {arXiv preprint arXiv:2608.02713},
  year    = {2026}
}
```
