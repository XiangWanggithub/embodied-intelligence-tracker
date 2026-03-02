# QVLA: Not All Channels Are Equal in Vision-Language-Action Model's Quantization

**arXiv**: [2026-02-03](https://arxiv.org/abs/...)  
**团队**: -

## 核心亮点

- **方向**: VLA 模型量化
- **发现**: VLA 量化时不同 channel 重要性不同
- **目标**: 更高效的 VLA 部署

## 关键问题

VLA 模型通常很大（7B+），如何在边缘设备高效部署？

## 结论

- 量化是 VLA 落地的重要路径
- 通道级量化策略优于全局量化
