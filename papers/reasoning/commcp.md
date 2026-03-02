# CommCP: LLM 多机器人通信协调框架

**arXiv**: [2026-02-05](https://arxiv.org/abs/2602.06038)  
**团队**: - (ICRA 2026)  
**重要度**: ⭐⭐  
**分类**: frameworks

## 一句话总结

用 Conformal Prediction 校准 LLM 生成的通信消息，提升多机器人协调效率。

## 解决的问题

多异构机器人执行复杂任务时，如何高效通信、避免冗余？

## 方法概述

- 去中心化通信框架
- LLM 生成通信消息
- Conformal Prediction 校准消息质量 → 减少干扰，提升可靠性
- 新 Benchmark: MM-EQA（多智能体多任务具身问答）

## 创新点

1. 将 Conformal Prediction 引入机器人通信
2. 去中心化架构，不依赖中心节点
3. 新的 MM-EQA benchmark

## 对我们的启发

- 多机器人协作的通信机制设计
- 去中心化 vs 中心化的权衡

## 相关链接

- 项目：https://comm-cp.github.io
