# H-AIM: LLM + PDDL + Behavior Trees 分层多机器人规划

**arXiv**: [2026-01-16](https://arxiv.org/abs/2601.11063)  
**团队**: -  
**重要度**: ⭐⭐⭐  
**分类**: frameworks

## 一句话总结

用 LLM + PDDL + Behavior Trees 三级联架构，实现异构多机器人长程任务规划。

## 解决的问题

- LLM 单独做规划：长程推理能力弱，动态协调差
- 传统规划器：不理解自然语言指令

## 方法概述

三级联架构：
1. **LLM 层**: 解析自然语言指令 → 生成 PDDL 问题描述
2. **Planner 层**: LLM 语义推理 + 经典规划器搜索 → 优化动作序列
3. **Execution 层**: 编译为 Behavior Trees → 反应式控制

关键设计：
- 共享黑板机制（Blackboard）用于多机器人通信和状态同步
- 支持动态大小的异构机器人团队

## 实验结果

- Benchmark: MACE-THOR（42 个复杂任务，8 种家庭布局）
- 对比 LaMMA-P：成功率 12% → 55%，目标条件召回 32% → 72%

## 对我们的启发

- **典型的 System 1 + System 2 实践**：LLM 做 System 2（推理规划），BT 做 System 1（反应式执行）
- PDDL 作为中间表示的价值：形式化但不失灵活性
- 多机器人协作的黑板机制值得借鉴
