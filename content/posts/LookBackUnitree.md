---
title: "Unitree MJLab 复盘"
date: 2026-06-29
draft: false
categories: ["具身智能"]
tags: ["具身智能","项目"]
---

本文档是作为unitree学习的回顾与分享

## unitree概述

unitree g1是宇树的人形机器人，目前我了解的内容主要是关于强化学习训练以及仿真的一些知识。






## 代码理解与上手实操指南



- 想改奖励参数（调整动作姿态）：修改legged_gym/envs/g1/g1_config.py的reward函数
- 想改训练参数（训练轮数等）：修改legged_gym/envs/g1/g1_config.py的G1RoughCfgPPO函数
- 想改训练算法：我认为是修改legged_gym/envs/base/legged_robot_config.py的LeggedRobotCfgPPO函数里的参数，G1Robot（legged_gym/envs/g1/g1_env.py）继承自LeggedRobot(unitree_rl_gym/legged_gym/envs/base/legged_robot.py) 继承自BaseTask(legged_gym/envs/base/base_task.py),存疑修改其他
- 想改动作精细度（增加关节等）：目前找到了num_observations，num_actions，control函数的控制参数（刚度和阻尼），修改机器人模型文件路径，在 __init__.py 中注册新任务，compute reward和observation函数也得修改，存疑修改其他
- 想训练它向前走：修改command函数



## 相关学习网站分享

强化学习教程：https://zhuanlan.zhihu.com/p/466455380

PPO教程：https://zhuanlan.zhihu.com/p/1911110735150416080

宇树官方代码：https://github.com/unitreerobotics

机器人相关参数以及开发指南：https://support.unitree.com/home/en/G1_developer/about_G1

mjlab官方教程（仿真相关参数学习）：https://mujocolab.github.io/mjlab/main/source/installation.html

分析.onnx网络结构：https://netron.app/?spm=5176.28103460.0.0.26fc2988Is2pY4


