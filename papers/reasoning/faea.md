# FAEA: Frontier Agent as Embodied Agent (零示范机器人控制)

**arXiv**: [2026-01-28](https://arxiv.org/abs/2601.20334)  
**团队**: -  
**重要度**: ⭐⭐⭐  
**分类**: frameworks

## 一句话总结

直接把通用 LLM Agent 框架（Claude Agent SDK）用于机器人操作，不需要任何示范数据。

## 解决的问题

VLA 模型需要大量 task-specific demo + fine-tuning，且 domain shift 后泛化差。

## 方法概述

- 用 Claude Agent SDK（原本用于软件工程的 Agent 框架）
- 直接接入机器人仿真环境
- LLM 用迭代推理（类似 debug 代码的方式）来推理操作策略
- **零示范**：不需要任何演示数据

## 实验结果

| Benchmark | 成功率 |
|-----------|--------|
| LIBERO | 84.9% |
| ManiSkill3 | 85.7% |
| MetaWorld | 96% |

加入一轮人类反馈后 LIBERO 达到 88.2%。

## 对我们的启发

- **颠覆性思路**：通用 Agent 框架可以直接做机器人控制
- 对于 deliberative（需要思考的）任务，LLM Agent ≈ VLA
- 可以用这种方式自动生成训练数据给 VLA
- 暗示了 System 2 型推理在机器人中的强大潜力

## 相关链接

- 代码：https://github.com/robiemusketeer/faea-sim
