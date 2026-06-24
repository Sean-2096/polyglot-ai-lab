# 学习基线

## 当前情况

| 项目 | 基线 |
|------|------|
| 每周可投入时间 | 5 小时 |
| Python | 掌握基础语法 |
| HTTP API | 调用过 |
| LLM 基础概念 | 了解 message、token、temperature |
| 技术英语 | 可以借助翻译阅读 |
| 日语 | 完全零基础 |
| 模型平台 | DeepSeek |

## 路线调整

根据当前基线，跳过通用 Python 入门和 HTTP 基础课程。

第一阶段重点是：

- 看清 DeepSeek 请求和响应的真实结构。
- 区分自己“听说过概念”和“能独立实现”。
- 建立英文官方文档的窄阅读方法。
- 日语从声音和文字系统开始，不进入项目代码。

## 每周 5 小时安排

| 内容 | 时间 |
|------|------|
| AI 示例、修改和重建 | 3 小时 30 分钟 |
| 英文官方资料阅读与复述 | 40 分钟 |
| 日语每日微训练 | 50 分钟 |

日语建议每周 5 天、每天 10 分钟。其余时间集中完成一个 AI 实验。

## 第一周目标

### AI

不用 LangChain 或 Web 框架，完成一次 DeepSeek 非流式请求，并能解释：

- API Key 如何进入请求。
- `base_url`、`model`、`messages` 分别控制什么。
- `system` 和 `user` 消息有什么区别。
- 请求成功和认证失败时分别发生什么。

### 英语

主要资料：

- [DeepSeek: Your First API Call](https://api-docs.deepseek.com/)

阅读问题：

1. Which SDK format is the DeepSeek API compatible with?
2. What are the official `base_url` and current model names?
3. Which field contains the generated answer?

本周只要求写 3～5 句英文总结。

### 日语

- 认识平假名、片假名和汉字三种文字。
- 学习五个元音：あ、い、う、え、お。
- 暂不学习日语编程词汇。

## DeepSeek 当前接口提醒

截至 2026-06-24，DeepSeek 官方 Quick Start 展示：

- OpenAI SDK 兼容地址：`https://api.deepseek.com`
- 当前模型：`deepseek-v4-flash`、`deepseek-v4-pro`
- `deepseek-chat` 和 `deepseek-reasoner` 计划于 2026-07-24 15:59 UTC 弃用

首个实验默认使用 `deepseek-v4-flash`，避免从即将弃用的模型名开始学习。

## L0-01 结论

当前能力足以直接进入模型调用实验，但实验必须保留从空文件重建环节。英语采用翻译辅助后再关闭翻译复读；日语采用独立微课程。
