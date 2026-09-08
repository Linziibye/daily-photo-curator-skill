# Daily Photo Curator

一个用于海报或摄影作品搜索、筛选和整理的 AI Skill。

用户只需要输入一句简单指令，例如：

> 帮我找一组随机主题的图片
> 给我一组海报

Skill 会自动完成主题选择、跨平台搜索、候选筛选、作品评分、系列整理、来源核验和最终交付。

默认每次生成一组 9 张摄影作品，可根据指令的不同进入海报模式或摄影模式。

海报模式偏向于寻找不同风格的海报作为灵感启发。

摄影模式偏向于寻找统一主题风格的摄影作品并命名为一个系列。

---

## 中文说明

### 功能

Daily Photo Curator 主要用于日常摄影/海报灵感收集和图片素材整理。

一次完整运行通常包含以下流程：

1. 自动确定当期主题，选择不同模式
2. 搜索多个摄影平台和图片来源
3. 建立候选图片池
4. 根据构图、光影、色彩、视觉冲击、氛围和技术质量进行筛选
5. 选择一张基准图
6. 提取基准图的审美 DNA
7. 根据审美方向进行第二轮搜索
8. 选出最终 9 张作品
9. 核验作者、来源、作品页面、许可和下载入口
10. 按统一格式整理输出
11. 检查库内文件，自动删除15天以前的历史文件

在连续使用时，Skill 可以结合可用的历史信息调整题材，增加不同摄影类别和视觉风格之间的轮换。

---

## 图片来源

完整运行会优先搜索多个摄影来源，包括：

- Pexels
- Unsplash
- Pinterest
- Flickr
- 摄影师个人作品页
- 摄影项目、机构或其他可靠摄影来源

最终作品按照图片质量、系列一致性、来源可靠性和使用信息进行综合筛选。

---

## 使用方式

安装或载入 Skill 后，可以直接输入：

> 帮我找图片

Skill 会自动选择主题并运行完整流程。

也可以指定主题：

> 帮我找一组猫咪摄影作品

> 帮我找黑白街头摄影

> 帮我找一些建筑摄影

> 帮我找酸性风格的海报

还可以增加具体要求：

> 帮我找9张可以用于商业项目的植物摄影

> 帮我找一组同一个摄影师的作品

> 帮我找一组暖色、电影感的人文摄影

用户给出的主题、风格、色彩、用途和数量要求会优先用于当次运行。

---

## 默认输出内容

一次标准运行会输出：

### 系列信息

- 系列艺术标题
- 1–3 句简短文案
- 当期主题
- 核心审美 DNA

### 9 张摄影或海报作品

每张作品包含：

- 中文展示名称
- 原作品名称
- 评分
- 作者
- 来源平台
- 简短策展说明
- 原作品页面
- 原图下载入口
  
支持图片直接展示的 AI 环境会同时提供最终作品预览。

---

## 文件交付

当运行环境支持图片下载和文件处理时，Skill 可以继续完成：

- 下载 9 张原图
- 按 01–09 顺序使用中文名称整理
- 生成 `作品来源与署名.txt`
- 创建统一文件夹
- 打包 ZIP
- 检查图片和压缩包完整性

标准文件结构：

```text
每日精选摄影/海报_YYYY-MM-DD_主题/
├── 01_作品名.jpg
├── 02_作品名.jpg
├── 03_作品名.jpg
├── 04_作品名.jpg
├── 05_作品名.jpg
├── 06_作品名.jpg
├── 07_作品名.jpg
├── 08_作品名.jpg
├── 09_作品名.jpg
└── 作品来源与署名.txt
```

## AI 环境兼容

Skill 采用能力自适应方式运行。

可以根据当前 AI 环境提供的功能选择相应的交付方式，包括：

- 图片预览 + 原图下载 + ZIP 素材包
- 图片预览 + 作品页面 + 原图下载入口
- 作品信息 + 作品页面 + 下载入口
- 摄影主题 + 审美方向 + 搜索关键词 + 策展方案

核心摄影筛选和策展规则保持一致，最终交付形式会根据当前环境能力自动调整。

这套工作流可以用于支持自定义 Skill、Prompt、Agent Instructions 或项目知识文件的 AI 环境，例如 ChatGPT、Gemini、DeepSeek、Grok、豆包及其他类似产品。

## 定时使用

Skill 每次调用会生成一期完整摄影精选。

支持定时任务或自动化功能的 AI 环境可以定期调用该 Skill，例如：

> 每天早上9点帮我找图片

也可以随时手动运行：

> 帮我找图片

## 默认语言

默认用户界面输出语言为简体中文。

作者名、平台名、原作品标题、许可证名称和链接会保留原始信息。

用户指定其他语言时，Skill 会按照当次语言要求输出。

---

# English

## Overview

Daily Photo Curator is an AI skill for photography discovery, curation, source verification, and organized delivery.

A simple request such as:

> Find images for me

starts a complete curation workflow.

The default result contains 9 selected photography works.

---

## Features

A standard run includes:

1. Theme selection
2. Multi-source photography search
3. Candidate-pool construction
4. Aesthetic screening
5. Photography scoring
6. Benchmark-image selection
7. Aesthetic-DNA extraction
8. Second-round discovery
9. Final selection of 9 works
10. Creator, source, license, and download verification
11. Structured delivery

The curation system evaluates composition, light, color, visual impact, atmosphere, narrative, technical quality, and series coherence.

---

## Sources

The workflow can search photography sources such as:

- Pexels
- Unsplash
- Pinterest
- Flickr
- Photographer portfolios
- Photography projects
- Institutional and other credible photography sources

Final selection is based on image quality, series coherence, source reliability, and usage information.

---

## Usage

Run the skill with a simple request:

> Find images for me

You can also specify a direction:

> Find a set of cat photographs.

> Find black-and-white street photography.

> Find architectural photography.

> Find a blue-toned photography collection.

Additional preferences such as subject, color, style, intended use, photographer, and image count can be included in the request.

---

## Standard Output

A standard collection includes:

- Artistic series title
- Short introduction
- Theme
- Sources searched
- Benchmark image
- Core aesthetic DNA
- 9 selected photography works

Each work can include:

- Chinese display title
- Original title
- Score
- Creator
- Source platform
- Curator note
- Original work page
- Verified download entry

AI environments with image-rendering support can also display the final images directly.

---

## File Delivery

When the host environment supports file operations, the skill can also:

- Download the 9 selected images
- Apply organized filenames
- Generate an attribution file
- Create a collection folder
- Build a ZIP archive
- Validate downloaded files and archive contents

---

## Capability-Adaptive Delivery

The skill adapts its output to the capabilities available in the current AI environment.

Possible delivery formats include:

1. Image previews + downloads + ZIP package
2. Image previews + source pages + download access
3. Structured work information + verified links
4. Theme + aesthetic direction + search terms + curation blueprint

The core curation methodology remains consistent across supported AI environments.

The workflow can be used with AI systems that support custom skills, prompts, agent instructions, or project knowledge, including ChatGPT, Gemini, DeepSeek, Grok, Doubao, and similar products.

---

## Scheduling

Each invocation produces one complete photography collection.

AI environments with scheduling or automation capabilities can invoke the skill on a recurring schedule.

Example:

> Run Daily Photo Curator every morning at 9:00.

Manual invocation can also be used at any time.

---

## Language

Simplified Chinese is the default user-facing language.

Creator names, platform names, original work titles, license names, and URLs are preserved in their original form where appropriate.

The skill follows another language when the user explicitly requests it.
