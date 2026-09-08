---
name: daily-photo-curator
description: Quickly curate and deliver a cohesive set of 9 real photographs, including exact previews, original work pages, verified original-image download links, copyright/source information, and a downloadable ZIP. Use for requests such as “find images,” “daily photography inspiration,” or “find a set of photographs.”
---

# Daily Photo Curator

## Goal

Complete one viewable, traceable, and downloadable photography collection per invocation.

By default, deliver exactly **9 real photographs** that are visually strong, thematically cohesive, and packaged into a ZIP containing the images and `作品来源与署名.txt`.

Use Simplified Chinese for all user-facing output by default. Follow another language only when the user explicitly requests it.

## Working Style

- Complete the task directly and efficiently. Do not show the search process, candidate pool, scoring process, or internal analysis.
- Do not stop after discovery or ask for confirmation between normal steps.
- Prioritize image quality over source convenience, platform balance, or ease of download.
- Never use AI-generated images, visually similar substitutes, guessed creator information, guessed work pages, guessed download links, or fabricated files.
- Follow a user-provided theme, colour direction, style, subject, platform, or use requirement first. When no direction is provided, choose one strong theme that can form a coherent nine-image series.

## Visual Quality and Cohesion

1. Choose one primary visual rule for the collection, such as:
   - one subject category;
   - one dominant colour system;
   - one lighting condition;
   - one photographic mood;
   - one compositional language.

2. Every final image must follow the primary visual rule and at least one supporting visual trait, such as colour, light, atmosphere, or composition.

3. Keep variation in viewpoint, shot scale, movement, or scene content. Avoid duplicate uploads, crops, mirrors, burst frames, and near-identical compositions.

4. Retain only images with immediate visual appeal, intentional composition, effective light, and clear save-worthy value. Reject visually ordinary, poorly composed, flatly lit, overly repetitive, or generic stock-like images.

5. Final scores should normally be at least 85/100. Display one overall score only; do not provide sub-scores.

6. Do not keep a weaker image merely to reach nine or because it is easier to download. If fewer than nine strong images are available after the initial review, perform one focused additional search or choose a stronger viable theme.

7. When the primary visual rule is a subject category, keep that subject category consistent across all nine images.

8. When image quality is comparable, prefer works from the same photographer or project if this strengthens cohesion without creating repetitive images.

## Selection and Sources

1. Prefer platforms with reliable downloads and complete creator and work-page information. Use Pexels by default; add Unsplash or another reliable source only when needed.

2. Quickly review approximately 12–18 candidate works and select the strongest, most cohesive nine.

3. Every final image must have:
   - a verified creator;
   - an original work page;
   - an official download entry for that exact photograph.

4. Each preview, listed metadata entry, original work page, download link, and downloaded file must refer to the exact same final photograph.

5. Preserve the creator’s original name and the original work title when available.

6. Record the actual licence or platform usage note when available. Do not infer commercial-use permission from download availability alone.

7. If the user explicitly requests commercial-use assets, retain only works with clearly compatible current licence or platform-use information.

8. Prefer the highest-quality file available through the verified official download entry.

## Downloading, Naming, and Packaging

1. Download all final images from verified official download entries. Download in parallel when supported.

2. Use a short timeout and no more than one retry per failed image. Replace a failed image promptly with another verified candidate that fits the same theme.

3. Confirm that every downloaded file:
   - exists;
   - is non-empty;
   - is identifiable as an image;
   - corresponds to its final selected work.

4. Preserve the original photographs. Do not crop, retouch, recolour, upscale, add text, or otherwise edit them.

5. Use the current Beijing date, UTC+8, unless the user specifies another timezone.

6. Name the collection folder:

   `每日精选摄影_YYYY-MM-DD_主题概括`

7. Name the image files:

   `01_中文作品名.jpg` through `09_中文作品名.jpg`

   Preserve the actual file format. If a downloaded file’s format differs from its filename extension, rename it using the real format.

8. Create `作品来源与署名.txt` inside the collection folder. Write it in Simplified Chinese and include:

   - series title;
   - theme;
   - Beijing date;
   - for each final image: filename, Chinese display title, original title, creator, source platform, work page, original-image download link, licence or platform-use note, and overall score.

9. Package the nine images and `作品来源与署名.txt` into a ZIP with the same base name as the folder:

   `每日精选摄影_YYYY-MM-DD_主题概括.zip`

10. Before packaging, confirm that the folder contains exactly nine readable image files and one `作品来源与署名.txt`.

11. After packaging, confirm that the ZIP opens correctly, contains all required files, and preserves readable Chinese filenames.

12. Treat viewing an image, opening its work page, downloading its file, and creating a ZIP as separate completed actions. Do not claim that a file or ZIP exists unless it was actually created and checked.

## Archive Cleanup

At the beginning of each run, check the Library for archives created by this skill.

- Only target files whose names exactly match:

  `每日精选摄影_YYYY-MM-DD_主题概括.zip`

- Only delete archives older than 15 full days, calculated using Beijing Time, UTC+8.
- Only delete files created by this skill. Do not delete folders, individual images, manually uploaded ZIP files, or files with uncertain origin.
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
   - the intended `01`–`09` image filenames.

## Final Output

Deliver the result directly in this order:

```markdown
《系列标题》(The title should be abstract, poetic, and visually appealing. It may draw inspiration from poetic associations from any culture. Only present a line as a quotation when its source is verified.)

Write 1–3 short, natural, abstract, poetic, and visually evocative sentences related to the title or its associations.

当期主题：……（简洁概括）

[按 01–09 顺序展示九张真实预览图]
（Each final photograph must be visibly previewed in the final response. Prefer displaying the downloaded local image through the conversation’s image-display capability; do not rely solely on external image URLs in Markdown as previews. If image display is unavailable, state this clearly and still provide the work page, original-image download link, and ZIP file.）

01_中文作品名.jpg｜XX分｜作者｜来源平台  
简介：一句话说明画面及其在系列中的作用。  
作品链接：[打开作品页](…)  
下载链接：[下载原图](…)

……

09_中文作品名.jpg｜XX分｜作者｜来源平台  
简介：一句话说明画面及其在系列中的作用。  
作品链接：[打开作品页](…)  
下载链接：[下载原图](…)

素材包下载：[同名 ZIP]
```

Keep the title concise and image-led. Avoid direct category labels such as “城市摄影” or “动物摄影”.

Write exactly one sentence for each image description. Do not add extra fields such as candidate analysis, sub-scores, memory points, creative points, or irreplaceability notes.

## Completion Standard

A run is complete only when all of the following are present:

- a poetic series title, short poetic copy, theme, and nine exact image previews;
- exactly nine real, visually strong, thematically cohesive photographs;
- for every image: filename, overall score, creator, source platform, one-sentence description, original work page, and original-image download link;
- a downloaded and verified ZIP containing nine image files and `作品来源与署名.txt`;
- consistent naming across the collection folder, images, TXT, and ZIP;
- cleanup of eligible archives older than 15 full days when Library access is available.
