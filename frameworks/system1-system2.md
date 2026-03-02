# System 1 / System 2 架构

> 快系统（实时控制）+ 慢系统（推理规划）  
> 更新时间：2026-03-02

## 核心概念

- **System 1**: 快速反射式控制，延迟 < 10ms
  - 例子：低层策略模型、阻抗控制、Behavior Trees
- **System 2**: 慢速推理规划，延迟秒级
  - 例子：LLM 任务分解、VLM 推理、PDDL 规划

## 最新实践

### H-AIM (2026-01) ⭐⭐⭐
LLM + PDDL + Behavior Trees 三级联架构：
- System 2: LLM 解析指令 + 规划器搜索最优序列
- System 1: Behavior Trees 反应式执行
- 成功率：12% → 55%（vs LaMMA-P）
→ [详细笔记](../papers/reasoning/h-aim.md)

### FAEA (2026-01) ⭐⭐⭐
通用 LLM Agent 直接做机器人控制（零示范）：
- 纯 System 2 方案：迭代推理 → 动作
- 对 deliberative 任务效果惊人（MetaWorld 96%）
- 暗示 System 2 推理比预想更强
→ [详细笔记](../papers/reasoning/faea.md)

### CommCP (2026-02) ⭐⭐
多机器人 LLM 通信协调：
- 去中心化通信 + Conformal Prediction 校准
- 解决多 Agent 冗余通信问题
→ [详细笔记](../papers/reasoning/commcp.md)

### pi_0.5 (2025)
分层 VLA：
- System 2: 高层 VLA 推理
- System 1: 低层扩散策略
- 解耦快慢系统

## 典型架构对比

| 方案 | System 2 | System 1 | 特点 |
|------|----------|----------|------|
| H-AIM | LLM + PDDL | Behavior Trees | 形式化，多机器人 |
| FAEA | LLM Agent (Claude SDK) | — | 纯推理，零示范 |
| pi_0.5 | 高层 VLA | 低层扩散策略 | 端到端，单机器人 |
| CommCP | LLM 通信 | 各自执行 | 去中心化 |

## 开放问题

1. **何时用 System 2？** FAEA 说推理够强，但延迟高
2. **接口设计**: 两系统之间的通信协议
3. **切换机制**: 什么时候从 System 1 升级到 System 2？
4. **World Models**: 综述指出 World Models 对安全部署不可或缺
