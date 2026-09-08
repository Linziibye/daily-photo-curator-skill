---
name: daily-photo-curator
version: 1.1.0
description: Curate and deliver a set of 9 real visual works for either cohesive photography inspiration or diverse poster-design research, including exact previews, original work pages, verified original-image download links, copyright/source information, and a downloadable ZIP. Use for requests such as “find photographs,” “daily photography inspiration,” “find posters,” “poster references,” or “graphic-design inspiration.”
---

# Daily Photo Curator

## Goal

Complete one viewable, traceable, and downloadable visual-reference collection per invocation.

By default, deliver exactly 9 real visual works that match the selected content mode and are packaged into a ZIP containing the images and a complete source-and-credit TXT file.

Select one content mode before searching:

- Photography Mode produces a cohesive photography series.
- Poster Mode produces either a diverse poster-learning reference collection or a focused collection within the user’s specified poster direction.

Use Simplified Chinese for all user-facing output by default. Follow another language only when the user explicitly requests it.

## Working Style

- Complete the task directly and efficiently. Do not show the search process, candidate pool, internal classifications, candidate comparisons, or internal analysis.
- Do not stop after discovery or ask for confirmation between normal steps.
- Prioritize visual quality, source traceability, and learning value over platform balance or ease of download.
- Never use AI-generated images, visually similar substitutes, guessed creator information, guessed work pages, guessed download links, or fabricated files.
- Follow a user-provided subject, colour direction, style, visual medium, platform, or use requirement first.
- When no direction is provided, use Photography Mode and choose one strong theme that can form a coherent nine-image series.
- Display one overall score only. Do not display sub-scores.

## Mode Selection

Before searching, select exactly one mode and keep it fixed for the entire run.

- Use Photography Mode when the request is about photographs, photography, landscapes, people, animals, architecture, a photography subject, or a cohesive visual photo series.
- Use Poster Mode when the request explicitly mentions posters, poster references, poster learning, graphic design, layout, typography, visual-design inspiration, exhibition posters, music posters, film posters, public-service posters, or campaign posters.
- If the user explicitly names a mode, follow it.
- If the request is genuinely ambiguous, use Photography Mode by default.
- Apply only the selected mode’s selection rules.
- Shared rules for source verification, downloading, naming, ZIP packaging, archive cleanup, fallback, and final delivery apply in both modes.

## Mode-Specific Naming and Delivery Contract

After selecting a mode, follow exactly one contract for the entire run. Use the selected contract in naming, source records, archive cleanup, fallback information, and final output.

### Photography Mode Contract

- Content type: 摄影作品
- Collection folder: `每日精选摄影_YYYY-MM-DD_主题概括`
- ZIP filename: `每日精选摄影_YYYY-MM-DD_主题概括.zip`
- Source-record filename: `摄影作品来源与署名.txt`
- Creator label: 摄影师
- Description focus: explain the image content and its role in the cohesive photographic series
- Final package label: 摄影素材包下载
- Archive-cleanup pattern: `每日精选摄影_YYYY-MM-DD_主题概括.zip`

### Poster Mode Contract

- Content type: 海报灵感
- Collection folder: `每日海报灵感_YYYY-MM-DD_主题概括`
- ZIP filename: `每日海报灵感_YYYY-MM-DD_主题概括.zip`
- Source-record filename: `海报来源与署名.txt`
- Creator label: 设计者 / 设计工作室
- Description focus: explain the core visual idea and one specific design method worth learning
- Final package label: 海报灵感素材包下载
- Archive-cleanup pattern: `每日海报灵感_YYYY-MM-DD_主题概括.zip`

For both modes, name image files from `01_中文作品名` through `09_中文作品名` and preserve the actual downloaded file extension.

## Photography Mode: Selection Logic

Use Photography Mode when the user requests real photographs, photography inspiration, a photography subject, or a cohesive visual photo series.

### Photography Visual Quality and Cohesion

1. Choose one primary visual rule for the collection, such as one subject category, dominant colour system, lighting condition, photographic mood, or compositional language.

2. Every final image must follow the primary visual rule and at least one supporting visual trait, such as colour, light, atmosphere, or composition.

3. Keep variation in viewpoint, shot scale, movement, or scene content. Avoid duplicate uploads, crops, mirrors, burst frames, and near-identical compositions.

4. Retain only images with immediate visual appeal, intentional composition, effective light, and clear save-worthy value.

5. Final scores should normally be at least 85/100.

6. Do not keep a weaker image merely to reach nine or because it is easier to download. If fewer than nine strong images are available after the initial review, perform one focused additional search or choose a stronger viable theme.

7. When the primary visual rule is a subject category, keep that subject category consistent across all nine images.

8. When image quality is comparable, prefer works from the same photographer or project if this strengthens cohesion without creating repetitive images.

### Photography Quality Standard

Assess each candidate internally using the following criteria:

1. Subject and visual focus:
   The image has a clear visual centre, an intentional subject relationship, or a compelling use of emptiness. The viewer can immediately understand where attention should go.

2. Composition and spatial control:
   Framing, scale, balance, depth, perspective, line, rhythm, and negative space create a deliberate visual structure. Avoid accidental cropping, cluttered backgrounds, weak horizons, and unfocused compositions.

3. Light, colour, and atmosphere:
   Light and colour support the image’s mood and subject. Retain works with expressive natural light, controlled contrast, meaningful tonal relationships, or a deliberate atmospheric treatment.

4. Technical and viewing quality:
   The downloaded image is clear and sufficiently detailed for viewing and saving. Avoid visible compression damage, severe blur, intrusive watermarks, poor exposure, broken colour, or other unintentional technical defects.

5. Distinctiveness and emotional value:
   The image offers a memorable visual moment, atmosphere, observation, or perspective. Avoid generic stock-like scenes unless the composition or light gives the work clear artistic value.

Use these criteria as a quick quality gate. Do not display sub-scores, internal classifications, or candidate comparisons. Give one overall score only, normally at least 85/100.

## Poster Mode: Selection Logic

### Poster Exploration

Use this sub-mode when the user asks for poster inspiration, poster-learning references, different posters to study, or general graphic-design references.

Select nine strong, real posters with clearly different visual approaches and learning value.

- Vary poster purpose, visual form, layout, or creative method whenever possible.
- Avoid near-duplicate posters, repeated templates, and works from the same campaign.
- Ensure any two final posters differ in at least two of these dimensions: communication purpose, visual form, layout approach, and creative method.
- Aim for at least six clearly distinct combinations across the final nine posters.
- Use no more than two works from the same designer, studio, or organisation.

### Focused Poster Research

Use this sub-mode when the user specifies a poster direction, such as acid posters, typographic posters, public-service posters, exhibition posters, music posters, film posters, collage posters, or a named design style.

- Treat the user’s specified direction as the primary visual rule.
- Keep the collection recognisably focused on that direction.
- Vary layout, scale, composition, typography, image treatment, or creative method within the chosen direction.
- Avoid near-duplicate posters, repeated templates, and works from the same campaign.
- Do not add unrelated poster styles merely to increase variety.

### Poster Quality Standard

In Poster Mode, select posters for professional design quality and transferable learning value.

Assess each candidate internally using the following criteria:

1. Communication and hierarchy: the poster has a clear focal point and an intentional reading order.

2. Concept and visual logic: the central visual idea has a meaningful relationship with the subject, message, or cultural context.

3. Composition and typographic control: layout, scale, spacing, alignment, contrast, colour, image treatment, and typography work as one controlled system.

4. Originality: the work contains a distinctive visual decision, such as an unexpected type-image relationship, spatial structure, material treatment, colour system, visual metaphor, or narrative device.

5. Learning value: a viewer can identify at least one transferable design method, such as hierarchy design, grid use, typography treatment, image-text interaction, colour control, material expression, or concept development.

Experimental, disruptive, or difficult-to-read layouts are acceptable when they are clearly intentional and support the work’s concept.

Retain only posters that are strong across these criteria. Final scores should normally be at least 85/100.

## Selection and Sources

1. Prefer platforms with reliable downloads and complete creator and work-page information.

2. For Photography Mode, prefer Pexels by default. Add Unsplash or another reliable photography source when needed.

3. For Poster Mode, prefer official designer, design-studio, cultural-institution, event-organisation, or publisher project pages. Use portfolio platforms only when the creator or studio and the exact project assets are clearly traceable.

4. Quickly review an appropriate candidate pool and retain only the strongest nine works for the selected mode.

5. Every final work must have:
   - a verified creator, designer, studio, photographer, or organisation;
   - an original work page;
   - an official download entry for that exact work.

6. Each preview, listed metadata entry, original work page, download link, and downloaded file must refer to the exact same final work.

7. Preserve the creator’s original name and the original work title when available.

8. Record the actual licence or platform-use note when available. Do not infer commercial-use permission from download availability alone.

9. If the user explicitly requests commercial-use assets, retain only works with clearly compatible current licence or platform-use information.

10. Prefer the highest-quality file available through the verified official download entry.

## Downloading, Naming, and Packaging

1. At the beginning of each run, complete archive cleanup according to the selected mode contract.

2. Download all final images from verified official download entries. Download in parallel when supported.

3. Use a short timeout and no more than one retry per failed image. Replace a failed image promptly with another verified candidate that fits the selected mode.

4. Confirm that every downloaded file:
   - exists;
   - is non-empty;
   - is identifiable as an image;
   - corresponds to its final selected work.

5. Preserve the downloaded source work. Do not crop, retouch, recolour, upscale, add text, or otherwise edit it.

6. Use the current Beijing date, UTC+8, unless the user specifies another timezone.

7. Use the selected mode contract for the collection folder, ZIP filename, and source-record filename.

8. Create the selected source-record TXT file inside the collection folder. Write it in Simplified Chinese and include:
   - series title;
   - content mode;
   - theme;
   - Beijing date;
   - for each final work: filename, Chinese display title, original title, creator or designer, source platform, work page, original-image download link, licence or platform-use note, and overall score;
   - for Poster Mode, include the project, client, event, or commissioning organisation when this information is available.

9. Package the nine images and the selected source-record TXT file into a ZIP with the same base name as the collection folder.

10. Before packaging, confirm that the folder contains exactly nine readable image files and one source-record TXT file.

11. After packaging, confirm that the ZIP opens correctly, contains all required files, and preserves readable Chinese filenames.

12. Treat viewing an image, opening its work page, downloading its file, and creating a ZIP as separate completed actions. Do not claim that a file or ZIP exists unless it was actually created and checked.

## Archive Cleanup

At the beginning of each run, check the Library only for archives created by the selected mode.

- In Photography Mode, only target files whose names exactly match:
  `每日精选摄影_YYYY-MM-DD_主题概括.zip`

- In Poster Mode, only target files whose names exactly match:
  `每日海报灵感_YYYY-MM-DD_主题概括.zip`

- Only delete archives older than 15 full days, calculated using Beijing Time, UTC+8.
- Only delete files created by this skill.
- Do not delete folders, individual images, manually uploaded ZIP files, or files with uncertain origin.
- Do not delete archives from the other mode.
- When recoverable deletion is supported, move eligible archives to Trash or Recycle Bin.
- If Library access or deletion is unavailable, skip cleanup and continue the current curation task.

## Fallback

If the current environment genuinely cannot complete all downloads and create a verified ZIP:

1. State the actual current limitation briefly and accurately.

2. Do not fabricate a ZIP or claim that files were downloaded.

3. Still deliver:
   - nine exact previews whenever supported;
   - nine verified original work pages;
   - nine verified original-image download links;
   - the intended collection folder name;
   - the intended ZIP filename;
   - the intended `01`–`09` image filenames.

## Final Output

Use the selected mode contract and deliver the result directly in this order:

```text
《系列标题》：与图片主题相关的，诗意或抽象、有美感的标题，可以是古今中外的诗句.

系列文案：1–3 句简短、自然、抽象且有画面感的文字，与图片主题，标题或其联想相关。

当期内容：摄影作品 / 海报灵感
当期主题：……（简洁概括）

[按 01–09 顺序展示九张真实预览图]

01_中文作品名.扩展名｜XX分｜摄影师 / 设计者｜来源平台
简介：一句话说明画面及其在摄影系列中的作用；或一句话说明海报的核心视觉创意及最值得学习的设计方法。
作品链接：[打开作品页](…)
下载链接：[下载原图](…)

……

09_中文作品名.扩展名｜XX分｜摄影师或设计者 / 设计工作室｜来源平台
简介：一句话说明画面及其在摄影系列中的作用；或一句话说明海报的核心视觉创意及最值得学习的设计方法。
作品链接：[打开作品页](…)
下载链接：[下载原图](…)

摄影素材包下载 / 海报灵感素材包下载：[同名 ZIP]

交付校验：（是否检查历史素材包；说明是否发现并清理超过 15 天且符合当前模式命名规则的 ZIP。本期 ZIP 是否验证可打开，且含 9 张可读取图片与完整署名清单。）
```

## Completion Standard

A run is complete only when all of the following are present:

- the correct content mode has been selected from the user’s request;
- the selected mode contract has been used consistently in naming, TXT records, cleanup, fallback information, and final output;
- a poetic series title, a separate `系列文案`, a content type, a theme, and nine exact image previews;
- exactly nine real, visually strong works selected according to the active mode;
- for every work: filename, overall score, creator or designer, source platform, one-sentence description, original work page, and original-image download link;
- a downloaded and verified ZIP containing nine image files and the correct source-record TXT file;
- consistent naming across the collection folder, images, TXT, and ZIP;
- archive cleanup of eligible files older than 15 full days when Library access is available;
- a final `交付校验` paragraph after the package link.

Before sending the final response, check every required field and complete any missing field.
