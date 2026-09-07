---
name: daily-photo-curator
description: Quickly curate and deliver a cohesive set of 9 real photographs, including previews, original work pages, original-image download links, and a downloadable ZIP. Use for requests such as “find images,” “daily photography inspiration,” or “find a set of photographs.”
---

# Daily Photo Curator

## Goal

Complete one viewable, traceable, and downloadable photography collection per invocation. By default, deliver **9 real photographs** that are visually strong and thematically cohesive, plus a ZIP containing the images and copyright/source information.

Use Simplified Chinese by default for user-facing output. Follow another language when the user explicitly requests it.

## Operating Principles

- Complete the task quickly. Do not show the search process or analysis process.
- Prioritize the photographs themselves: retain only images with immediate visual appeal, sound composition and lighting, and clear save-worthy value.
- The collection must have one clear theme. The nine images must share at least two of the following: subject, colour, light, atmosphere, or compositional language. Preserve variation in viewpoint, shot scale, or scene content, and avoid repetitive frames.
- Do not use AI-generated images, similar-image substitutes, guessed creator information, guessed work pages, or guessed download links.
- Follow a user-provided theme, colour direction, style, subject, or platform first. When no direction is provided, choose one that can form a strong nine-image series.

## Selection and Sources

1. Prefer platforms with reliable downloads and complete creator and work-page information. Use Pexels by default; add Unsplash or another reliable source only when needed.
2. Quickly review approximately 12–18 candidate works and select the strongest, most cohesive 9. Do not require cross-platform coverage, multiple search rounds, a benchmark image, aesthetic-DNA analysis, a rejected-candidate report, or category-by-category scoring.
3. Every final image must have a creator, an original work page, and an official download entry for that exact work. The page information and download entry must refer to the same photograph.
4. Display one overall score only, on a 100-point scale. Use it to express relative quality; do not provide sub-scores.

## Downloading, Naming, and Packaging

1. Download the final 9 images from verified official download entries. Confirm that every file exists, is non-empty, and is identifiable as an image.
2. Name the collection folder: `每日精选摄影_YYYY-MM-DD_主题概括`
3. Name the images from `01_中文作品名.jpg` to `09_中文作品名.jpg`. Preserve the actual file format; if the downloaded format differs from its extension, rename it using the real format.
4. Create `作品来源与署名.txt`. Include the series title, theme, date, and for every image: filename, Chinese display title, original title, creator, source platform, work page, original-image download link, licence note, and overall score.
5. Package the 9 images and TXT into a ZIP with the same name as the folder: `每日精选摄影_YYYY-MM-DD_主题概括.zip`.
6. Before packaging, confirm that the folder contains exactly 9 images and 1 TXT file. After packaging, confirm that the ZIP opens correctly, contains all required files, and preserves readable Chinese filenames.
7. When an image download fails, replace it with another candidate that fits the same theme. If the environment genuinely cannot complete all downloads and create the ZIP, state this accurately and still deliver 9 previews, work pages, and official download links. Never fabricate a ZIP.

## Final Output

Deliver the result directly in this order:

```markdown
《系列标题》

The title should be abstract, poetic, and visually appealing. It may draw inspiration from poetic associations from any culture. Only present a line as a quotation when its source is verified.

Write 1–3 short, natural, abstract, poetic, and visually evocative sentences related to the title or its associations.

当期主题：……（简洁概括）

[Display the 9 real image previews in 01–09 order]

01_中文作品名.jpg｜XX分｜Creator｜Source Platform  
简介：One sentence describing the image and its role in the collection.  
作品链接：[打开作品页](…)  
下载链接：[下载原图](…)

……

09_中文作品名.jpg｜XX分｜Creator｜Source Platform  
简介：……  
作品链接：[打开作品页](…)  
下载链接：[下载原图](…)

素材包下载：[同名 ZIP]
```

Keep the title concise and image-led. Avoid category labels such as “City Photography” or “Animal Photography.” Write only one sentence for each image description and do not add extra fields.

## Completion Standard

A run is complete only when all of the following are present:

- A title, poetic copy, theme, and 9 image previews;
- Exactly 9 real photographs of consistent theme and sufficient quality;
- For every image: name, overall score, creator, description, work page, and original-image download link;
- A downloaded and packaged ZIP containing 9 images and `作品来源与署名.txt`;
- Consistent naming across the collection folder, images, and ZIP.
