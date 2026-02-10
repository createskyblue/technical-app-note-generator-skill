---
name: technical-app-note-generator
description: Convert technical discussions into structured, atomic Application Notes. Generates independent txt files optimized for technical documentation. Language adapts to user preference (Chinese or English).
---

# Technical Application Note Generator

将技术讨论内容转化为结构化、原子化的应用笔记（Application Notes），每篇笔记生成独立的TXT纯文本文件。语言根据用户偏好自动适配。

## 何时使用

- 整理嵌入式系统、RTOS、电源管理等技术讨论内容
- 需要生成专业、简洁的技术文档片段
- 要求输出为纯文本格式，便于版本控制
- 需要每篇笔记聚焦单一技术概念

## 使用方法

### 输入参数

- **topic**: 技术主题或核心概念（如"FreeRTOS电源管理"）
- **key_points**: 需要展开的技术要点列表，每个要点对应一个独立TXT文件
- **max_words_per_note**: 单篇笔记正文字数上限（默认300字）
- **output_directory**: TXT文件输出目录路径（默认"./notes"）

### 工作流程

1. **分析输入要点**: 解析key_points，确保每个要点具备独立成篇的技术深度
2. **生成元数据**: 为每个要点创建技术标题（5-15个字符或术语），并生成对应的txt文件名。标题语言与用户输入语言保持一致
3. **撰写正文**: 撰写250-300字的技术正文
4. **质量校验**: 检查字数、扫描表情符号、验证原子性
5. **文件生成**: 将每篇笔记写入独立的.txt文件

### 内容结构

- **首句**: 定义概念或阐明原理
- **中段**: 技术细节、实现机制或关键参数
- **末段**: 设计影响、约束条件或最佳实践

### 文件名格式（SEO优化）

```
{seo_title}.txt
```

文件名生成规则：
- **语言适配**：根据用户使用语言决定（中文用户使用中文术语，英文用户使用英文术语）
- 格式：主题关键词 + 核心概念 + 技术要点
- 长度：15-30个字符（不含扩展名）
- 使用下划线连接各部分
- 包含关键搜索词，便于AI智能体检索

文件名示例（中文）：
- `FreeRTOS电源管理_电源管理器任务优先级设置.txt`
- `STM32时钟系统_PLL锁相环配置详解.txt`
- `嵌入式低功耗设计_引用计数实现机制.txt`

文件名示例（English）：
- `FreeRTOS_Power_Manager_Task_Priority_Configuration.txt`
- `STM32_Clock_System_PLL_Configuration_Guide.txt`
- `Embedded_Low_Power_Reference_Counting_Mechanism.txt`

冲突处理：若文件名重复，添加`_v2`、`_v3`等版本后缀

### 输出格式

纯文本格式，仅包含标题和正文：

```
[标题]

[正文内容，250-300字]
```

## 约束规则

- **原子性**: 每篇笔记严格遵循"一事一议"
- **字数**: 正文控制在250-300字之间
- **结构**: 仅两级结构（标题+正文），禁止三级标题或列表嵌套
- **纯净文本**: 严禁使用表情符号、ASCII艺术、富文本标记
- **技术语调**: 专业、客观，避免口语化，禁止人称代词
- **文件隔离**: 每个要点生成独立的.txt文件

## 参考

- 详细规则和示例: `references/detailed-rules.md`
- 输出示例: `references/examples.md`
