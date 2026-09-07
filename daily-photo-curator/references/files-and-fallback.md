# Files, Packaging, and Fallback Rules

## 1. Purpose

This reference defines how `Daily Photo Curator` handles:

- verified image downloading;
- download retries;
- file validation;
- Chinese filename generation;
- attribution metadata;
- collection-folder creation;
- ZIP packaging;
- ZIP verification;
- technical failures;
- current-run error reporting;
- capability-adaptive delivery;
- partial-download handling;
- archive cleanup.

This file governs:

> **What happens after the photographs have been selected and verified, and how the Skill adapts when the host cannot complete file operations.**

Photography selection and aesthetic evaluation are governed by:

`references/curation.md`

Source discovery, creator verification, licensing, previews, work pages, download-entry verification, and final presentation are governed by:

`references/source-and-delivery.md`

---

# 2. Core File-Handling Principle

File delivery must be based on actual execution.

The Skill MUST distinguish between:

- finding a photograph;
- opening its work page;
- identifying a download entry;
- displaying an image;
- downloading an image file;
- validating that file;
- creating a ZIP;
- validating that ZIP.

These are separate operations.

Success at one stage MUST NOT be treated as proof that later stages succeeded.

For example:

> An image displaying successfully in a webpage does not prove that the file was downloaded into the host's file environment.

Similarly:

> A verified download link does not prove that the file was successfully downloaded.

---

# 3. Capability Detection

Before performing file operations, determine what the current host environment can actually do.

Relevant capabilities may include:

- access external URLs;
- follow download links;
- download binary files;
- create local or sandbox files;
- inspect file size;
- determine file type;
- open or decode images;
- rename files;
- create text files;
- create directories;
- create ZIP archives;
- extract ZIP archives;
- persist files across runs;
- delete or move files to a recoverable trash location.

MUST NOT assume these capabilities exist.

If a required capability is unavailable, use the highest applicable fallback delivery level.

---

# 4. Delivery Levels

The Skill uses four capability-adaptive delivery levels.

Always use the **highest level that can be completed reliably in the current run**.

## Level 4 — Full Download Package

Use when the host can reliably:

- discover and verify real photographs;
- access legitimate download entries;
- download binary image files;
- create local files;
- validate images;
- create text files;
- create ZIP archives;
- verify ZIP archives.

Deliver:

- direct image previews when supported;
- complete 9-image collection;
- original work pages;
- verified download entries;
- 9 actual downloaded image files;
- Chinese filenames;
- `作品来源与署名.txt`;
- validated ZIP package.

## Level 3 — Preview + Verified Download Access

Use when the host can:

- discover and verify real works;
- display the selected works;
- verify legitimate download entries;

but cannot reliably download/package the files itself.

Deliver:

- direct image previews;
- complete 9-image collection;
- creator/source information;
- original work pages;
- verified download entries.

Do not create or claim a ZIP.

## Level 2 — Verified Link Delivery

Use when the host can:

- discover real works;
- verify creators and source pages;
- verify download entries;

but cannot reliably render images or package files.

Deliver:

- 9 selected works;
- Chinese display titles;
- creator information;
- source platform;
- score;
- concise curator commentary;
- original work pages;
- verified download entries.

## Level 1 — Curation Blueprint

Use only when the host cannot access live external image sources.

Deliver:

- theme;
- artistic title;
- visual direction;
- Aesthetic DNA;
- recommended sources;
- search terms;
- target characteristics;
- screening rules.

Clearly state that real works, creators, URLs, licenses, and downloads could not be verified.

MUST NOT fabricate them.

---

# 5. Level Selection Rule

Do not downgrade prematurely.

If one specific file operation fails:

1. identify the affected step;
2. retry only the affected item or operation;
3. preserve all successful work;
4. attempt legitimate alternative routes where available;
5. downgrade only when the higher delivery level cannot be completed reliably.

Example:

If 8 images download successfully and 1 fails:

- do not immediately abandon all downloaded files;
- retry the failed image;
- try another legitimate download route for the same photograph;
- replace the photograph only if appropriate and source integrity can be maintained;
- preserve the eight successful downloads.

---

# 6. Verified Download Source Requirement

Only attempt file downloading from a legitimate verified download source.

A valid download source may be:

- an official platform download button;
- an actual redirect produced by that button;
- a verified original-file URL exposed by the work page;
- a creator-provided file;
- another authoritative download route for the exact selected photograph.

MUST NOT download from:

- a guessed CDN path;
- a URL constructed from a photo ID;
- a manually altered thumbnail URL;
- a pattern inferred from another photograph;
- a source that cannot be matched to the selected work.

Download convenience MUST NOT override source integrity.

---

# 7. Download Attempt Sequence

For each of the final photographs:

1. identify the verified download entry;
2. attempt the legitimate primary download route;
3. record whether the download actually succeeds;
4. validate the resulting file;
5. if the attempt fails, inspect the actual failure;
6. retry using another legitimate route for the same work when available;
7. if no reliable route succeeds, apply the relevant partial-failure rule.

Do not repeatedly retry the same failed route without reason.

Do not construct new URLs in an attempt to bypass the failure.

---

# 8. Per-Image Retry Rule

A failed image download SHOULD receive a reasonable retry when:

- another official download control exists;
- an official redirect is available;
- the work page exposes another legitimate resolution;
- the creator or platform provides another verified file route;
- the first attempt appears to have failed transiently.

Retry only the failed work.

Do not restart the entire 9-image workflow unless necessary.

---

# 9. Current-Run Failure Evidence

Technical failure claims must be based on errors actually observed during the current execution.

Valid examples include:

- DNS resolution failure;
- connection timeout;
- connection refusal;
- HTTP 403;
- HTTP 404;
- HTTP 429;
- server 5xx response;
- authentication requirement;
- redirect failure;
- malformed response;
- returned HTML instead of image data;
- file-write failure;
- permission error;
- invalid image file;
- archive-creation failure;
- archive-verification failure.

MUST NOT reuse a failure from an earlier run as evidence for the current run.

---

# 10. Specific Error Reporting

When file delivery fails, report the most specific useful error available.

Good:

> 第06张原图下载请求返回 HTTP 403，因此本次未能保存该图片文件。

Good:

> 当前文件环境无法解析 `images.example.com`，实际下载请求出现 DNS resolution failure。

Good:

> 第03张下载结果为 HTML 页面而非图片文件，因此未计入成功下载。

Avoid vague statements such as:

> 跨站图片无法下载。

> 网络有问题。

> 系统限制导致失败。

> 图片网站不支持打包。

Only state what was actually observed.

---

# 11. Web Access vs File Download Access

Treat browsing access and file-download access as separate capabilities.

A host may be able to:

- search the web;
- open a work page;
- display an image;

while still being unable to:

- resolve the image CDN from its file environment;
- download the binary file;
- save it locally.

Therefore:

> Browser success ≠ file-environment success.

Do not infer one from the other.

---

# 12. HTTP Status Handling

When an actual HTTP status is observed:

## 403 Forbidden

The host reached the server but access was denied.

Possible response:

- try another official route;
- use the work-page download control;
- preserve link-based delivery if available.

Do not characterize 403 as DNS failure.

## 404 Not Found

The requested resource does not exist at that URL.

Do not guess a replacement URL.

Return to the authoritative work page and locate a legitimate route.

## 429 Too Many Requests

The source is rate-limiting requests.

A reasonable later or alternate legitimate route MAY be attempted during the current run.

Do not repeatedly hammer the source.

## 5xx Server Error

Treat as a source-side or transient failure unless stronger evidence exists.

Preserve verified metadata and downgrade file delivery if necessary.

---

# 13. DNS Failure Handling

If the current execution produces an actual DNS resolution failure:

- identify the affected hostname where possible;
- report that exact current-run failure;
- do not claim the user's local computer DNS is broken;
- do not generalize the failure to every website;
- do not assume the failure is permanent;
- do not use a previous DNS failure as proof of a current one.

Example:

> 本次文件环境在请求 `images.example.com` 时出现 DNS 解析失败，因此无法将该原图保存到本地文件环境。

If webpage browsing still works, preserve:

- previews;
- source pages;
- verified download entries;

and downgrade file packaging only.

---

# 14. Timeout Handling

If a request times out:

- report the affected item;
- distinguish timeout from DNS or HTTP rejection;
- retry only when reasonable;
- use another legitimate route if one exists.

Do not claim a site is permanently unavailable because one request timed out.

---

# 15. HTML Error-Page Detection

A file ending in `.jpg`, `.jpeg`, `.png`, or another image extension is not automatically a real image.

After downloading, verify that the file contains actual image data.

Reject files that are actually:

- HTML error pages;
- login pages;
- rate-limit pages;
- redirect pages;
- bot-challenge pages;
- JSON error responses;
- empty files.

Do not package these as images.

---

# 16. Image File Validation

Every downloaded final image SHOULD be validated before packaging.

Check, where technically possible:

- file exists;
- file size is greater than zero;
- file size is reasonable for an image;
- MIME type or file signature is consistent with an image;
- image can be opened or decoded;
- dimensions are plausible;
- file is not a webpage or error document;
- file corresponds to the intended selected work.

When possible, inspect the actual image rather than relying only on filename extension.

---

# 17. Original-Quality Preference

Prefer the highest legitimate quality available through the verified download route.

Do not deliberately use:

- tiny thumbnails;
- search-result preview images;
- heavily compressed screenshot substitutes;

when an official higher-quality file is available.

However:

- do not bypass access controls;
- do not construct hidden high-resolution URLs;
- do not violate platform restrictions merely to obtain a larger file.

---

# 18. Filename Rules

When actual files are created, rename the nine final images in the same 01–09 order used in the user-facing result.

Default format:

`01_中文作品名.ext`

through:

`09_中文作品名.ext`

Examples:

- `01_尘里迎面而来.jpg`
- `02_金色赛道.jpg`
- `03_水岸扬尘.jpg`

Filename requirements:

- preserve the actual valid extension;
- use concise Chinese display titles;
- avoid characters prohibited by common file systems;
- avoid excessively long filenames;
- preserve 01–09 numeric ordering.

---

# 19. Filename Sanitization

When required by the operating system, replace or remove invalid filename characters such as:

`\ / : * ? " < > |`

Prefer readable replacements.

Example:

Original display title:

> 城市：雨后

Safe filename:

`01_城市·雨后.jpg`

Do not allow filename sanitation to change the identity or ordering of the work.

---

# 20. Collection Folder Naming

Use one consistent naming convention.

Default folder name:

`每日精选摄影_北京时间YYYY-MM-DD_主题简短概括`

Example:

`每日精选摄影_北京时间2026-09-07_暮色奔马`

Use the user's requested timezone if explicitly specified.

Otherwise, for the default Chinese edition of this Skill, use Beijing Time when a timezone is needed and the host can determine it reliably.

If the exact timezone cannot be determined, do not fabricate a precise date label.

---

# 21. ZIP Naming

The ZIP archive MUST use the same base name as the collection folder.

Example:

Folder:

`每日精选摄影_北京时间2026-09-07_暮色奔马`

ZIP:

`每日精选摄影_北京时间2026-09-07_暮色奔马.zip`

This naming convention should also be used by any archive-cleanup rule.

Do not maintain conflicting naming patterns between creation and cleanup.

---

# 22. Attribution File

When file creation is supported, generate:

`作品来源与署名.txt`

Place it inside the collection folder and ZIP archive.

The file should be written in Simplified Chinese unless the user explicitly requests another language.

---

# 23. Attribution File Content

The attribution file SHOULD begin with collection-level metadata.

Example structure:

```text
系列标题：
当期主题：
生成日期：
基准图：
核心审美 DNA：
实际搜索平台：
最终平台构成：
```

Then record every final work.

For each work include:

```text
01_中文作品名.jpg

中文展示名：
原作品名：
作者：
来源平台：
原始作品页：
原图下载入口：
许可：
总分：

构图与空间：
光影：
色彩与调色：
视觉冲击与记忆点：
氛围与叙事：
技术与质感：

是否为基准图：
主体类别：
与基准审美 DNA 的匹配点：
创意/惊艳满足项：
记忆点：
不可替代点：
```

At the end, record:

```text
实际搜索平台：
未进入最终清单的主要来源/平台及主要淘汰原因：
文件下载状态：
ZIP验证状态：
```

---

# 24. Attribution Accuracy

Metadata in `作品来源与署名.txt` must match the final delivered collection.

MUST NOT include:

- candidates that were ultimately rejected;
- incorrect creators;
- guessed licenses;
- guessed download URLs;
- outdated replaced works;
- filenames that differ from the packaged files.

Before packaging, confirm:

`TXT metadata = final 9 works = packaged files`

---

# 25. Folder Contents

A standard complete Level 4 collection folder should contain exactly:

- 9 final image files;
- `作品来源与署名.txt`.

Example:

```text
每日精选摄影_北京时间2026-09-07_暮色奔马/
├── 01_尘里迎面而来.jpg
├── 02_金色赛道.jpg
├── 03_水岸扬尘.jpg
├── 04_白马破沙.jpg
├── 05_日落以前群山沉默.jpg
├── 06_光从马群之间穿过.jpg
├── 07_她从暮色里转身.jpg
├── 08_涉过最后一道光.jpg
├── 09_暮色收走蹄声.jpg
└── 作品来源与署名.txt
```

Do not include:

- failed downloads;
- HTML error files;
- temporary files;
- unrelated images;
- candidate images that were not selected;
- duplicate images;
- hidden working files;

unless the user explicitly requests additional materials.

---

# 26. ZIP Creation

Only create the ZIP after all intended folder contents have been validated.

ZIP creation sequence:

1. verify the nine final image files;
2. verify `作品来源与署名.txt`;
3. verify filenames and numbering;
4. verify folder naming;
5. create ZIP;
6. verify ZIP exists;
7. test archive readability;
8. inspect archive contents;
9. confirm exact required contents;
10. only then expose the ZIP to the user.

---

# 27. ZIP Validation

A ZIP is not considered successfully delivered merely because archive creation returned without an obvious error.

Validate where technically possible that:

- ZIP file exists;
- ZIP size is greater than zero;
- archive can be opened;
- archive can be extracted or enumerated;
- exactly 9 intended image files are present;
- `作品来源与署名.txt` is present;
- no invalid error-page files are included;
- filenames are readable;
- extracted files are accessible.

Only after this validation may the Skill state:

> ZIP 已生成并验证。

---

# 28. ZIP Integrity Requirement

MUST NOT provide:

- empty ZIP;
- placeholder ZIP;
- archive containing URLs instead of images while claiming it contains images;
- archive containing HTML error pages;
- archive containing fewer than the promised files without explanation;
- untested ZIP while claiming successful verification;
- fabricated download path.

If ZIP validation fails, report the actual failure and use fallback delivery.

---

# 29. Partial Download Failure

If some images download successfully and others fail:

1. preserve successfully validated images;
2. identify failed image numbers;
3. retry failed works through legitimate alternate routes;
4. replace a work only if needed and consistent with curation quality;
5. revalidate any replacement;
6. create a complete ZIP only if all required final files are successfully obtained.

Do not silently package an incomplete collection as a complete 9-image package.

---

# 30. Partial Package Delivery

If a complete ZIP cannot be created but some files are successfully available:

MAY provide the successful files individually if the host supports that delivery.

Also provide verified download entries for the remaining works.

Clearly distinguish:

- 已成功下载
- 需要用户通过链接下载

Do not label a partial package as a complete ZIP.

---

# 31. Replacement Rule

A photograph MAY be replaced after final selection when:

- its source cannot be verified;
- licensing becomes incompatible;
- the download source fails permanently during the current run;
- the file cannot be validated;
- another serious integrity problem is discovered.

Replacement MUST:

- still satisfy the current subject rule;
- fit the Aesthetic DNA;
- meet the quality threshold;
- undergo source verification;
- undergo file validation if packaged.

Do not replace a failed work with a weaker photograph merely for convenience unless no better valid alternative exists.

---

# 32. Fallback Order

When Level 4 cannot be completed, downgrade in this order:

`Level 4 → Level 3 → Level 2 → Level 1`

Do not skip to Level 1 simply because ZIP generation failed.

Example:

If:

- web search works;
- exact images are verified;
- image previews work;
- download links are verified;
- local file download fails;

then use **Level 3**, not Level 1.

Preserve every capability that still works.

---

# 33. Standard Level 4 Completion Message

When all files and ZIP are actually validated, the delivery may include:

> **ZIP下载：** 已生成并完成完整性验证。

Then provide the actual file or host-supported download link.

Do not use this wording unless validation actually occurred.

---

# 34. Standard Level 3 Fallback Message

When previews and verified download entries are available but file packaging fails:

Use a concise explanation such as:

> **ZIP下载：** 本次文件环境无法完成全部原图落盘与ZIP验证，已保留9张作品预览、原作品页和经核验的下载入口。

If a specific error occurred, include it.

Example:

> **ZIP下载：** 本次文件环境请求图片CDN时出现DNS解析失败，因此无法生成经过验证的ZIP；已提供9张作品预览、原作品页及可核验下载入口。

Only use the specific error if observed in the current run.

---

# 35. Standard Level 2 Fallback Message

When real works and download entries are verified but inline previews are unavailable:

> 当前环境无法可靠地在对话中直接展示最终图片，因此本期采用链接交付；9张作品均提供已核验的作品页面及可用下载入口。

Do not use visually similar substitute images.

---

# 36. Standard Level 1 Fallback Message

When the host cannot access live external sources:

> 当前环境不具备实时外部图片检索能力，因此无法可靠核验真实作品、作者、作品页和下载链接。本次将提供完整的策展主题、审美DNA、搜索关键词与筛选方案，不虚构具体图片来源。

---

# 37. Fixed Fallback Integrity

Fallback wording must reflect the actual current execution.

MUST NOT use a generic fixed sentence containing a technical cause that was not observed.

For example, do not automatically say:

> “因DNS问题无法生成ZIP”

merely because a previous run experienced DNS failure.

The cause must be verified during the current run.

---

# 38. Do Not Treat Cross-Platform Sourcing as Failure

The fact that photographs come from multiple websites is not itself a technical problem.

MUST NOT say:

> “因为图片来自多个平台，所以无法打包。”

A Level 4 environment can package files from multiple legitimate sources if downloads succeed.

Only report the actual technical reason for failure.

---

# 39. Do Not Fabricate File Paths

Only provide a downloadable local/sandbox file link when the file actually exists in the host environment.

MUST NOT invent:

- local file paths;
- sandbox links;
- download URLs;
- ZIP filenames pretending to exist;
- cloud-storage links.

If file creation did not occur, provide verified external download entries instead.

---

# 40. Do Not Confuse Planned and Completed Files

The Skill may know the intended filename before downloading.

That does not mean the file exists.

Distinguish:

> 应使用文件名：`01_尘里迎面而来.jpg`

from:

> 已生成文件：`01_尘里迎面而来.jpg`

Only use the second when the file actually exists.

---

# 41. File Extension Integrity

Preserve or derive file extensions from the actual validated image format.

Common extensions may include:

- `.jpg`
- `.jpeg`
- `.png`
- `.webp`

Do not rename a WEBP binary to `.jpg` merely for visual consistency unless the file is actually converted.

If conversion is performed, validate the converted output.

---

# 42. Optional Format Normalization

If the host supports reliable image conversion, MAY normalize all final files to one common format.

For example:

`01_作品名.jpg`

However:

- conversion is optional;
- original image quality should be preserved;
- metadata and orientation should not be corrupted;
- conversion must not be claimed unless performed.

Default behavior should prefer preserving the original validated format.

---

# 43. Duplicate File Validation

Before ZIP creation, confirm that the nine image files are distinct.

Check where possible:

- file hashes;
- image dimensions;
- visual content;
- source identity.

Do not package the same binary file under multiple filenames.

Near-duplicate selections are governed by `curation.md`.

---

# 44. Image Orientation

Do not alter orientation merely to make the collection visually uniform.

Preserve the original photographic composition.

If EXIF orientation causes incorrect display, MAY normalize orientation without changing the actual crop or composition.

Do not crop images automatically unless the user explicitly requests it.

---

# 45. No Unrequested Image Editing

Downloading and packaging must preserve the selected photographic works.

MUST NOT automatically:

- recolor;
- retouch;
- sharpen;
- denoise;
- upscale;
- crop;
- remove watermarks;
- alter composition;
- add text;
- apply filters.

This Skill is a photography-curation workflow, not an image-editing workflow.

---

# 46. Watermarked Files

Do not deliberately package watermarked preview files as “original images” when legitimate originals are unavailable.

If only a watermarked preview can be accessed:

- use it only as a visual reference if appropriate;
- clearly identify the limitation;
- do not label it as original download.

---

# 47. File Size Sanity Check

When technically possible, use file size as one validation signal.

Suspicious examples:

- `0 bytes`;
- a few hundred bytes for a supposed full-resolution photograph;
- unexpectedly tiny file containing an error response.

File size alone is not proof of validity.

Combine it with image decoding or MIME/file-signature checks where possible.

---

# 48. TXT Encoding

Generate `作品来源与署名.txt` using a Unicode-compatible encoding, preferably UTF-8.

The Chinese text should remain readable after:

- ZIP extraction;
- transfer;
- opening on common operating systems.

Avoid encodings likely to corrupt Chinese characters.

---

# 49. ZIP Filename Encoding

When creating ZIP archives, preserve Chinese filenames correctly.

Where the host provides control over ZIP encoding, prefer UTF-8-compatible filename handling.

After archive creation, verify that Chinese filenames remain readable.

---

# 50. User-Specified Packaging Overrides

If the user explicitly requests:

- no ZIP;
- only links;
- only preview;
- another naming scheme;
- English filenames;
- PNG only;
- a different folder name;
- separate folders;
- no attribution TXT;

follow the user's request where technically and legally valid.

Explicit user requirements override the default packaging format.

---

# 51. Persistent Storage

Persistent storage is optional.

The Skill MUST NOT require persistent storage for normal execution.

If persistent storage is available, it MAY be used for:

- current collection files;
- run history;
- archive management.

Do not assume files remain available in future runs unless persistence is actually supported.

---

# 52. Historical Archive Cleanup

Archive cleanup is an optional maintenance behavior and must only operate when the host has appropriate persistent file access.

Only consider archives generated by this Skill using the exact naming pattern:

`每日精选摄影_北京时间YYYY-MM-DD_主题简短概括.zip`

The cleanup rule MUST NOT expand to unrelated files.

---

# 53. Cleanup Eligibility

An archive may be eligible for cleanup only when all of the following are true:

- filename matches the Skill's exact ZIP naming convention;
- archive was generated by this Skill;
- archive contains the expected photography-package structure;
- archive age exceeds 15 days using the applicable timezone;
- the host supports a recoverable deletion or trash mechanism;
- cleanup is authorized by the user's workflow or explicit instruction.

Do not infer ownership merely from a vaguely similar filename.

---

# 54. Recoverable Cleanup Only

When performing automatic cleanup:

Prefer:

> move to recoverable trash / recycle bin

over:

> permanent deletion.

MUST NOT permanently delete historical archives unless the user explicitly requests permanent deletion and the host permits it.

---

# 55. Cleanup Scope

Cleanup applies only to this Skill's historical photography-package archives.

MUST NOT delete:

- unrelated ZIP files;
- manually created photography folders;
- arbitrary images;
- user documents;
- source materials;
- files with uncertain origin;
- archives that merely contain the words “每日精选摄影” but do not match the exact naming rule.

When uncertain, leave the file untouched.

---

# 56. Cleanup Failure

If cleanup cannot be performed because the host lacks:

- persistent file access;
- trash support;
- date metadata;
- permission;

skip cleanup.

This does not affect the current photography curation run.

Do not present cleanup inability as a failure of the Skill itself.

---

# 57. No Background Assumption

The Skill MUST NOT assume it can perform background maintenance.

If the host supports scheduled or automated maintenance and the user has requested it, cleanup MAY be included in that external workflow.

Without such support, cleanup occurs only during an actual invocation where the relevant files are accessible.

---

# 58. Package Status Reporting

At the end of the final user-facing output, clearly distinguish package state.

Possible states include:

## Complete

> **素材包状态：** 9张原图与署名文件均已下载、校验并完成ZIP验证。

## Link Delivery

> **素材包状态：** 当前环境无法生成可靠ZIP，已提供9张作品的预览、作品页及经核验下载入口。

## Partial

> **素材包状态：** 其中7张已成功保存，02与06因本次下载失败未能落盘；已提供对应官方下载入口，因此本次未生成完整ZIP。

## No Live Access

> **素材包状态：** 当前环境无法访问实时图片来源，因此本次未进行真实文件下载。

Never report a higher completion state than actually achieved.

---

# 59. Failure Is Local, Not Global

A failure affecting one capability should not unnecessarily invalidate the entire run.

Examples:

- ZIP failure does not invalidate image selection.
- File download failure does not invalidate verified source pages.
- Preview failure does not invalidate verified download links.
- One inaccessible platform does not invalidate candidates from other searched platforms.

Preserve all valid completed work.

---

# 60. No Silent Degradation

When the Skill falls below the highest expected delivery level, briefly tell the user what changed.

Example:

> 本期策展与来源核验已完成，但当前环境无法进行文件落盘，因此采用“预览 + 原图下载入口”交付。

Keep this concise.

Do not overwhelm the final answer with implementation details.

---

# 61. Package Quality Checklist

Before declaring Level 4 completion, verify:

## Downloads

- [ ] Exactly the intended final photographs were downloaded.
- [ ] Every downloaded file exists.
- [ ] Every file has non-zero size.
- [ ] Every file is valid image data.
- [ ] No HTML/error pages are present.
- [ ] No unverified thumbnail is labeled as original.
- [ ] Downloaded files correspond to the selected works.

## Naming

- [ ] Files are numbered 01–09.
- [ ] Chinese display filenames are valid.
- [ ] Extensions correspond to actual formats.
- [ ] No duplicate filenames exist.

## Metadata

- [ ] `作品来源与署名.txt` exists.
- [ ] TXT is readable in Chinese.
- [ ] Metadata matches the final collection.
- [ ] Creator/source/license fields are accurate.
- [ ] Scores and Irreplaceable Points match the selected works.

## Folder

- [ ] Folder name follows the defined naming convention.
- [ ] Folder contains exactly 9 target images plus the TXT.
- [ ] No unrelated temporary files remain.

## ZIP

- [ ] ZIP exists.
- [ ] ZIP has non-zero size.
- [ ] ZIP can be opened.
- [ ] ZIP contents can be enumerated or extracted.
- [ ] ZIP contains exactly the expected final files.
- [ ] Chinese filenames remain readable.
- [ ] Extracted images remain valid.

Only after all applicable checks pass may Level 4 be declared complete.

---

# 62. Fallback Checklist

Before downgrading delivery, verify:

- [ ] The higher-level capability was genuinely unavailable or failed.
- [ ] The failure occurred in the current run.
- [ ] Reasonable legitimate retries were attempted where appropriate.
- [ ] Successful work was preserved.
- [ ] No download URL was fabricated.
- [ ] No ZIP was fabricated.
- [ ] The highest remaining reliable delivery level was selected.
- [ ] The user received as much usable output as the environment supports.

---

# 63. Final Integrity Standard

The file-delivery stage should optimize for:

1. real files;
2. correct files;
3. complete files;
4. verified files;
5. convenient packaging.

Convenience is last.

A beautifully formatted ZIP containing incorrect, broken, guessed, or unverified files is a failed result.

A link-based collection containing nine correctly verified photographs is preferable to a fabricated “complete package.”

---

# 64. Final User Experience Standard

When the host supports full execution, the desired experience is:

> **用户说一句“帮我找图片”，AI完成摄影策展、来源核验、原图下载、中文命名、署名整理、ZIP打包与完整性检查，用户最终直接获得一套可查看、可追溯、可下载的9图摄影灵感包。**

When the host cannot support every technical step:

> **保持同一套策展质量，只降低当前环境确实无法实现的交付功能。**

The Skill should fail gracefully, truthfully, and minimally.

Never fabricate completeness.
