# 分层架构

> 多层次模型协作，每层负责不同抽象级别的任务  
> 更新时间：2026-03-02

## 典型分层

```
指令层 (Instruction)  ← LLM：自然语言理解
      ↓
规划层 (Planning)     ← PDDL / LLM：任务分解、序列优化
      ↓
技能层 (Skill)        ← 技能库：Pick, Place, Push...
      ↓
控制层 (Control)      ← 低层策略：关节控制、位姿跟踪
```

## 最新代表性工作

### H-AIM (2026-01) ⭐⭐⭐
三级联架构：LLM → PDDL Planner → Behavior Trees
- 指令层：LLM 解析自然语言 → PDDL 问题
- 规划层：LLM 语义 + 经典规划器搜索
- 控制层：Behavior Trees 反应式执行
- 亮点：共享黑板机制支持多机器人
→ [详细笔记](../papers/reasoning/h-aim.md)

### Agentic AI Survey (2026-01) ⭐⭐
统一分类框架：Perception → Brain → Planning → Action → Tool → Collaboration
- 从单 Agent 到多 Agent 层级系统
- 覆盖具身机器人领域
→ [详细笔记](../papers/survey/agentic-ai.md)

### Spatial AI Agents Survey (2026-02) ⭐⭐⭐
三轴分类：Capability × Task × Scale
- 关键发现：分层记忆系统对长程任务很重要
- GNN-LLM 融合用于结构化空间推理
→ [详细笔记](../papers/survey/spatial-ai-agents.md)

## 架构对比

| 维度 | 端到端 VLA | 分层框架 |
|------|-----------|---------|
| 延迟 | 慢（大模型推理） | 快（简单任务跳过高层） |
| 泛化 | 依赖数据量 | 依赖接口设计 |
| 可解释 | 低（黑盒） | 高（每层可检查） |
| 工程复杂度 | 低 | 高（层间通信） |
| 代表 | pi_0, OpenVLA | H-AIM, FAEA |

## 趋势

1. **LLM 作为高层规划器**已成共识
2. **形式化中间表示**（PDDL, BT）有回归趋势
3. **多机器人协作**需要新的通信机制
4. **World Models** 作为安全层的重要性上升
