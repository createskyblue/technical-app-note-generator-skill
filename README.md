# Technical Application Note Generator

Convert technical discussions into structured, atomic Application Notes. Language adapts to user preference (Chinese or English).

## Features

- **Auto-generate technical notes**: Transform scattered technical discussions into professional application notes
- **Plain text output**: Generate independent .txt files for version control and searchability
- **AI-searchable**: SEO-optimized filenames for intelligent agent retrieval
- **Atomic focus**: Each note covers exactly one technical concept

## Use Cases

- Organize embedded systems, RTOS, power management discussions
- Convert meeting notes or technical exchanges into archivable documents
- Build personal technical knowledge base for future reference

## Output Characteristics

- 250-300 words per note, concise and focused
- Plain text format, no rich text markup
- SEO-optimized filenames with technical keywords
- Professional and objective technical documentation tone

## Filename Examples

**Chinese:**
```
FreeRTOS电源管理_电源管理器任务优先级设置.txt
STM32时钟系统_PLL锁相环配置详解.txt
嵌入式低功耗设计_引用计数电源管理机制.txt
```

**English:**
```
FreeRTOS_Power_Manager_Task_Priority_Configuration.txt
STM32_Clock_System_PLL_Configuration_Guide.txt
Embedded_Low_Power_Reference_Counting_Mechanism.txt
```

## Usage

Provide when invoking the skill:
- **topic**: Technical topic (e.g., "FreeRTOS Power Management")
- **key_points**: List of technical points, each generates one file
- **output_directory**: Output directory (optional, default "./notes")

## Smart Duplicate Detection

Before creating new notes, the skill automatically:
- Scans existing notes in the output directory
- Detects similar notes by comparing keywords and technical concepts
- **Requires your decision** when similarity > 70%:
  - **Merge**: Append to existing note
  - **New Filename**: You provide a new filename (no auto _v2, _v3 suffixes)
  - **Skip**: Cancel this note
  - **View**: Check existing content first

**No automatic version numbers** - You always decide the final filename. This keeps your knowledge base clean and meaningful.

## Language Adaptation

The skill automatically detects and adapts to the user's preferred language:
- Chinese input → Chinese output (中文文件名和内容)
- English input → English output (English filenames and content)
- Mixed input → Follows the dominant language of the topic
