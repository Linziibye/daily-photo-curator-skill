# Source Verification and Delivery Rules

## 1. Purpose

This reference defines how `Daily Photo Curator`:

- discovers photography works across multiple sources;
- verifies creators and original work pages;
- handles Pinterest and other discovery-only sources;
- checks licenses and usage status;
- verifies download entries;
- prevents source and URL fabrication;
- presents selected works to the user;
- generates artistic titles and short introductory copy;
- displays image previews when supported;
- structures the final 01–09 photography collection;
- reports source composition and verification limitations.

This file governs:

> **Where the photographs come from, how their identities are verified, and how the final collection is presented.**

Photography-quality judgment is governed by:

`references/curation.md`

Actual file downloading, validation, ZIP packaging, and technical fallback behavior are governed by:

`references/files-and-fallback.md`

---

# 2. Fundamental Source Principle

Every final photograph presented as a real, verified work must correspond to an identifiable real source.

For every final photograph, the Skill should establish as much of the following chain as the host environment permits:

`Photograph → Creator → Original Work Page → Source Platform → License / Usage Status → Verified Download Entry`

The integrity of this chain is more important than producing a visually perfect-looking answer.

If any part cannot be verified:

- state the limitation;
- preserve the verified information;
- do not invent missing information.

---

# 3. Cross-Platform Discovery Requirement

For a full real-image curation run with adequate web-search capability, search across multiple photography sources.

The default discovery set SHOULD include:

1. Pexels
2. Unsplash
3. Pinterest
4. at least one additional credible photography source

The additional source may include:

- Flickr;
- photographer portfolios;
- photography project websites;
- museum collections;
- gallery collections;
- photography magazines;
- editorial photography platforms;
- photography communities;
- public-domain collections;
- other credible sources appropriate to the current theme.

Do not stop searching merely because one source already provides nine usable photographs.

The purpose of cross-platform search is:

- broader visual competition;
- reduced platform bias;
- better photographer discovery;
- better thematic variety;
- higher probability of finding exceptional work.

Platform diversity is a **discovery requirement**, not a final allocation quota.

---

# 4. No Platform Quotas

Do not force artificial source balance.

Do not require:

- exactly 3 Pexels images;
- exactly 2 Unsplash images;
- exactly 2 Flickr images;
- exactly 2 images from other sources.

The final nine MAY come primarily from one platform if its works genuinely outperform the alternatives.

Selection priority is:

1. photographic quality;
2. aesthetic fit;
3. source verifiability;
4. license suitability;
5. delivery usability;
6. platform diversity.

Platform balance MUST NOT override image quality.

---

# 5. Search Integrity

Only claim that a platform was searched when the current execution actually searched it.

MUST NOT say:

> “本次搜索了 Pexels、Unsplash、Pinterest 和 Flickr”

unless those sources were genuinely searched during the current run.

If a required source cannot be searched because of:

- host limitations;
- site blocking;
- tool restrictions;
- authentication requirements;
- inaccessible pages;
- other technical limitations;

report only the sources actually searched.

Do not fabricate cross-platform coverage.

---

# 6. Pexels Handling

Pexels MAY serve as:

- a discovery source;
- a final work source;
- a download source when a legitimate download entry is available.

For a final Pexels work, verify where possible:

- photograph identity;
- creator;
- original Pexels work page;
- current usage/license information;
- actual download entry.

Do not infer an original-image URL merely from:

- photo ID;
- thumbnail URL;
- known URL pattern;
- previously observed Pexels structure.

A legitimate download entry must come from:

- an actual work page;
- a real download control;
- a verified redirect;
- another verifiable source belonging to that exact work.

Platform policies may change over time.

When license or commercial-use suitability matters, verify the current terms rather than relying on remembered platform policy.

---

# 7. Unsplash Handling

Unsplash MAY serve as:

- a discovery source;
- a final work source;
- a download source when a legitimate download route is available.

For each final Unsplash work, verify where possible:

- exact photograph;
- creator;
- original work page;
- current license or usage terms;
- download entry.

Do not construct direct image URLs or download URLs from assumed patterns.

If the platform exposes a download action or download-location mechanism, use only an actually verified route.

Do not claim that an Unsplash work is suitable for a particular commercial use without checking the current applicable terms when that distinction matters.

---

# 8. Pinterest Handling

Pinterest should primarily function as a **visual discovery and source-tracing layer**.

Pinterest is particularly useful for discovering:

- photographers;
- photography projects;
- visual directions;
- editorial series;
- unusual compositions;
- high-level visual references;
- works that can later be traced elsewhere.

A Pinterest image MUST NOT automatically be treated as:

- the original source;
- proof of authorship;
- proof of licensing;
- a verified downloadable final work.

Before a Pinterest-discovered photograph enters the final verified collection, attempt to trace it to:

1. the original photographer;
2. the photographer's website or portfolio;
3. the original project;
4. the original publication;
5. a credible photography platform;
6. another authoritative source.

If tracing fails:

- MAY retain the image as a discovery reference;
- MUST NOT silently present it as a fully verified downloadable final work.

Do not use a Pinterest pin alone as proof of copyright ownership or permitted usage.

---

# 9. Flickr Handling

Flickr MAY contain photographs under many different licenses.

Never assume:

> “Flickr 图片都是 Creative Commons。”

For every Flickr work considered for final delivery, inspect the license attached to that specific work where possible.

Record the exact license name when verified.

Examples may include:

- All Rights Reserved;
- Creative Commons licenses;
- public-domain-related designations;
- other platform-supported licenses.

Different photographs from the same creator MAY have different licenses.

License verification must be performed per work.

If a work has restrictions such as:

- attribution;
- non-commercial use;
- share-alike;
- no derivatives;

do not hide those restrictions.

Explain them accurately when they materially affect user use.

---

# 10. Other Photography Sources

Other credible sources MAY be used when they improve the collection.

Examples include:

- photographer portfolios;
- Magnum-style documentary archives;
- museum photography collections;
- gallery websites;
- photography publications;
- editorial projects;
- public-domain archives;
- cultural institutions;
- photography competitions;
- photographer-hosted project pages.

For each final work from such a source, attempt to establish:

- creator;
- original or authoritative page;
- source identity;
- current rights or usage information;
- download availability if applicable.

Do not assume that a publicly visible image is free to download or reuse.

---

# 11. Original Source Hierarchy

When multiple pages contain the same photograph, prefer the most authoritative source.

Use approximately this priority:

1. photographer's original portfolio/project page;
2. authoritative publisher or project page;
3. credible photography platform hosting the creator's work;
4. institutional or archival source;
5. secondary editorial source;
6. discovery-only source such as Pinterest.

Do not replace a clearly identifiable original source with a less authoritative repost merely because the repost is easier to access.

---

# 12. Creator Verification

For every final work, verify the creator where possible.

Creator information may come from:

- original work page;
- photographer portfolio;
- official platform attribution;
- authoritative publication;
- institutional metadata.

Preserve creator names in their original spelling.

Do not translate personal names unless an established translation is clearly available and useful.

Do not invent:

- photographer names;
- account names;
- publication credits;
- usernames.

If creator identity cannot be confirmed, state:

> 作者信息未能可靠核验

rather than guessing.

---

# 13. Work Identity Verification

Before finalizing a photograph, make sure that all displayed information refers to the same work.

The following must not be mismatched:

- preview image;
- Chinese display title;
- original title;
- creator;
- original work page;
- source platform;
- license;
- download entry.

The Skill MUST NOT combine metadata from two visually similar photographs.

If multiple photographs from the same series look similar, verify the exact selected image.

---

# 14. Original Work Page Verification

A final work page should be:

- the exact page for the selected photograph;
- a credible original or authoritative page;
- actually opened or otherwise verified when browsing tools permit.

Do not construct work-page URLs based on:

- guessed slugs;
- photo IDs;
- platform URL conventions;
- search-result snippets;
- assumed photographer usernames.

If the exact work page cannot be established:

- do not fabricate one;
- state that the original work page could not be reliably verified.

---

# 15. License and Usage Verification

Licensing must be treated as work-specific and time-sensitive.

Where relevant, verify:

- current platform terms;
- specific work license;
- attribution requirements;
- commercial-use restrictions;
- modification restrictions;
- redistribution restrictions;
- share-alike obligations;
- other meaningful conditions.

Do not simplify:

> “能下载”

into:

> “可以随便商用”

These are different claims.

When the user explicitly requests:

> “只要可商用图片”

then licensing suitability becomes a hard selection constraint.

In that case:

- verify commercial-use suitability;
- eliminate works with incompatible or unclear permissions;
- report meaningful attribution or usage obligations.

If the user does not specify commercial use, still record the known license or usage status where practical.

---

# 16. License Language

Preserve official license names where possible.

Examples:

- `Unsplash License`
- `Pexels License`
- `CC BY 4.0`
- `CC BY-NC-SA 3.0`
- `Public Domain`
- `All Rights Reserved`

User-facing explanations should be in Simplified Chinese.

Example:

> 许可：CC BY 4.0  
> 使用说明：允许分享和改编，包括商业使用，但需要按许可要求署名。

Do not paraphrase legal permissions beyond what can be supported.

When uncertain, provide the license name and advise the user to inspect the source terms rather than inventing certainty.

---

# 17. AI-Generated and Synthetic Imagery

The default purpose of this Skill is to curate real photography.

Exclude works that are clearly:

- AI-generated;
- synthetic;
- virtual photography;
- rendered CGI presented as photography;
- heavily generated composites where the work no longer functions as ordinary photography;

unless the user explicitly requests synthetic or AI-generated visual references.

If authenticity is uncertain:

- investigate when possible;
- avoid presenting uncertain synthetic imagery as verified real photography.

---

# 18. Download Entry Verification

A verified download entry must correspond to the exact final work.

Acceptable sources include:

- actual platform download button;
- verified download redirect;
- verified original-file link exposed by the work page;
- legitimate creator-provided download;
- another verifiable original-file source.

MUST NOT:

- construct a download URL;
- guess a CDN path;
- extrapolate from another photograph's URL;
- alter image IDs to produce a presumed original file;
- provide a thumbnail URL while calling it “原图下载”.

A download entry may be a page or action rather than a raw file URL if that is the legitimate verified download mechanism.

---

# 19. Preview Integrity

When the host supports direct image rendering, show the actual final selected works whenever possible.

The preview must correspond to the same photograph as:

- the listed creator;
- original work page;
- source platform;
- download entry.

MUST NOT use:

- a similar photograph;
- another photograph from the same photographer;
- a generic search result;
- an AI recreation;
- a generated approximation;
- an unrelated thumbnail.

If exact direct preview cannot be guaranteed, prefer a link-based delivery over displaying a misleading substitute.

---

# 20. Direct Preview Requirement

For hosts with reliable direct image-display capability, the final collection SHOULD visually present all final works inside the conversation.

The intended experience is:

`直接看图 → 阅读作品信息 → 打开原作品页 → 下载原图`

A user should not need to open nine separate pages merely to understand what was selected.

However:

- preview capability is host-dependent;
- absence of preview does not make the Skill fail;
- missing preview should trigger capability-adaptive delivery rather than fabricated images.

---

# 21. Search Result Images vs Final Work Images

Search-engine thumbnails may be used during discovery.

They MUST NOT automatically become final previews.

Before using a search-result image as a final preview, verify that it corresponds to:

- the exact final work;
- the verified work page;
- the correct creator.

If that correspondence cannot be established, do not use the thumbnail as final visual evidence.

---

# 22. Final Collection Title

Every standard collection should have an **artistic series title**.

The title is separate from the technical theme.

Example:

Theme:

> 马群 × 奔跑 × 尘雾 × 逆光

Artistic title:

> 《尘土记得它们经过》

The artistic title SHOULD be:

- concise;
- evocative;
- visually suggestive;
- connected to the actual photographs;
- memorable;
- natural in Chinese;
- restrained enough to avoid melodrama.

Avoid titles that are merely category labels.

Weak:

- 《马匹摄影》
- 《城市街头》
- 《花卉微距》
- 《建筑摄影》

Better:

- 《尘土记得它们经过》
- 《灯灭以前》
- 《玻璃后的另一座城》
- 《叶脉里藏着一场雨》

---

# 23. Title Style

Titles MAY use:

- original poetic phrasing;
- visual metaphor;
- spatial imagery;
- light imagery;
- temporal imagery;
- subtle personification;
- restrained emotional language.

Avoid:

- generic motivational language;
- internet cliché;
- exaggerated emotional manipulation;
- excessive sentimentality;
- empty ornate wording;
- forced philosophical depth;
- deliberately obscure titles with little connection to the photographs.

The title should strengthen the experience without distracting from the photographs.

---

# 24. Literary References

If using or adapting literary language:

- verify the source;
- preserve accurate attribution;
- do not invent quotes;
- do not invent authors;
- do not invent translations;
- do not present original AI-written language as a historical quotation.

Prefer:

- original writing;
- public-domain literary references;
- short, accurately attributed references.

Avoid substantial quotation from copyrighted modern works.

---

# 25. Poetic Introduction

After the artistic title, provide a short introduction of approximately **1–3 sentences**.

Its purpose is to create an emotional entry into the series.

It SHOULD:

- evoke atmosphere;
- reflect the selected photographs;
- be concise;
- use natural Chinese;
- complement the visual direction.

It SHOULD NOT:

- explain the search process;
- explain scoring;
- discuss technical implementation;
- read like a project report;
- list photographic techniques.

Example:

> 风没有留下形状。  
> 只有鬃毛、蹄声和被夕阳扬起的尘埃，短暂地证明它曾经经过。

---

# 26. Theme Field

After the title and short introduction, clearly identify the current theme.

Recommended format:

> **当期主题：** 马群 × 奔跑 × 尘雾 × 逆光 × 野性动态

The theme should describe the actual visual direction more concretely than the artistic title.

It may include:

- subject;
- visual style;
- color;
- lighting;
- mood;
- movement;
- photographic language.

---

# 27. Platforms Actually Searched

Report only platforms actually searched during the current execution.

Recommended format:

> **实际搜索平台：** Pexels、Unsplash、Pinterest、Flickr

If some expected source was inaccessible:

> **实际搜索平台：** Pexels、Unsplash、Flickr  
> Pinterest 本次因当前环境无法访问，未计入候选池。

Do not imply a search occurred when it did not.

---

# 28. Benchmark Image Presentation

Clearly identify the benchmark image.

Recommended format:

> **基准图：** 05｜《日落以前，群山沉默》｜95分｜Osman Arabacı

Then provide a concise explanation of why it anchors the series.

Do not reveal private internal reasoning.

Provide only curator-facing conclusions such as:

- strongest visual anchor;
- defines color direction;
- defines motion;
- defines spatial structure;
- establishes atmosphere.

---

# 29. Aesthetic DNA Presentation

Summarize the benchmark Aesthetic DNA concisely.

Recommended format:

> **核心审美 DNA：** 群体主体、中远景、低角度暖色逆光、扬尘形成空气层次、强方向性运动、土黄与深棕色体系、前景—主体—远景多层空间、真实而具有电影感的动态。

Do not dump the entire internal analysis unless requested.

The user-facing Aesthetic DNA should normally be one concise paragraph or compact line.

---

# 30. Standard Final Output Order

Unless the user explicitly requests a different structure, present a complete real-image curation result in this order:

1. 系列艺术标题
2. 1–3句诗意短文案
3. 当期主题
4. 实际搜索平台
5. 基准图
6. 核心审美 DNA
7. 最终9张作品直接预览（宿主支持时）
8. 01–09作品详情
9. 最终平台构成
10. 下载 / ZIP 状态

Do not lead with a long explanation of methodology.

The user should see the curated result quickly.

---

# 31. Final Image Preview Layout

When the host supports visual rendering, present all final works clearly.

Possible layouts include:

- 9-image grid;
- carousel;
- sequential large previews;
- other host-supported visual presentation.

The layout should prioritize:

- image visibility;
- easy comparison;
- correspondence between image and numbered entry.

If possible, preserve the 01–09 order used in the detailed entries.

---

# 32. Standard Work Entry

Each final work should follow a consistent structure.

Recommended format:

```text
01_中文作品名.jpg｜93分｜作者｜来源平台
原作品名：Original Work Title

简短策展说明……

记忆点：……
创意点：……
不可替代点：……

作品页面：……
原图下载：……
许可：……
# 33. Chinese Display Title

Every final photograph SHOULD receive a concise Chinese display title.

The Chinese display title:

- does not replace the official original title;
- may be an editorial display title created for the collection;
- should reflect the actual image;
- should remain concise and visually evocative.

Avoid overly long titles.

Filename example:

`01_尘里迎面而来.jpg`

If the original title is useful, preserve it separately:

> 原作品名：Horses Running in Dust

---

# 34. Score Display

Display the final total score.

Example:

> `93分`

The user-facing result normally does not need to show all six sub-scores unless:

- the user requests them;
- detailed scoring improves the task;
- the metadata file requires them.

The full six-dimensional score belongs primarily in `作品来源与署名.txt` when file packaging is available.

---

# 35. Curator Commentary

Each work should receive approximately **1–2 concise sentences** of curator-facing explanation.

The commentary should cover the most relevant combination of:

- content;
- composition;
- color;
- lighting;
- atmosphere;
- relationship to the series;
- visual memory point;
- creative distinction;
- Irreplaceable Point.

Avoid repetitive descriptions such as:

> “这张构图很好，光影很好，颜色也很好。”

Prefer specific observations.

Example:

> 马群从尘雾中迎面压近，主体尺寸和扬起的沙尘共同制造出强烈的前冲感；它为整组建立了最直接的野性和速度感。

---

# 36. Memory Point

Every final work should have a clear **记忆点**.

Examples:

- face partially hidden by reflection;
- horse emerging from dust;
- isolated red umbrella in monochrome street;
- bird wings aligned with horizon;
- shadow dividing architecture into two geometric fields;
- dancer suspended at peak motion.

The memory point answers:

> **第一眼之后，我最容易记住什么？**

---

# 37. Creative Point

Where appropriate, include a concise **创意点**.

The creative point may describe:

- composition;
- timing;
- visual coincidence;
- reflection;
- scale;
- abstraction;
- color relationship;
- unusual perspective;
- subject interaction;
- other meaningful invention.

If the work qualifies primarily through visual impact rather than obvious conceptual novelty, do not invent a creative point.

It is acceptable to write:

> 创意点：以决定性瞬间和空间关系取胜，未依赖明显的概念式构造。

---

# 38. Irreplaceable Point in Delivery

Every final work MUST communicate its **不可替代点** either:

- explicitly as a field;
- or clearly within the curator commentary.

Recommended explicit format:

> **不可替代点：** 前景马匹的逆光轮廓与后方扬尘形成三层空间，同时所有主体保持同向运动，使这张图成为整组最强的速度锚点。

Avoid generic statements such as:

> “非常有氛围。”

---

# 39. Original Work Page

Every verified final work SHOULD include:

> **作品页面：** [verified page]

The page must correspond to the exact selected work.

If unavailable:

> **作品页面：** 未能可靠核验

Do not replace missing information with an invented URL.

---

# 40. Original-Image Download Entry

When a legitimate download route is verified, provide:

> **原图下载：** [verified download entry]

If a raw direct file URL cannot be reliably verified but an official work-page download button exists, the download entry may refer to the legitimate official route.

If no legitimate downloadable source is available:

> **原图下载：** 当前未找到可可靠核验的官方下载入口

Do not fabricate a direct image URL for presentation convenience.

---

# 41. License Field

Where license information is verified and useful, provide:

> **许可：** Pexels License

or:

> **许可：** CC BY 4.0

If the work has meaningful restrictions, briefly explain them in Chinese.

If uncertain:

> **许可：** 当前未能可靠核验，请以原作品页最新条款为准

Do not invent license certainty.

---

# 42. Commercial-Use Requests

If the user explicitly asks for:

- commercial-use images;
- advertising material;
- brand-use images;
- unrestricted commercial assets;

then source and license verification becomes stricter.

Final works MUST satisfy the requested use as far as reliably verifiable.

Exclude:

- clearly non-commercial licenses;
- clearly incompatible restrictions;
- unverifiable licensing when commercial-use certainty is required.

If only a subset can be fully verified, prefer replacing uncertain works rather than weakening licensing integrity.

---

# 43. Source Metadata Preservation

Preserve original metadata accurately.

Do not unnecessarily translate:

- creator names;
- usernames;
- platform names;
- original titles;
- license names;
- project names.

Chinese explanatory fields may be added around them.

Example:

> 作者：Zeynep Sude Emek  
> 来源：Pexels  
> 原作品名：Horses Running in Dust  
> 中文展示名：《尘里迎面而来》

---

# 44. Platform Composition Summary

At the end of a complete collection, summarize the source composition.

Example:

> **本期平台构成：** Pexels 5张、Unsplash 2张、Flickr 2张。

If one platform dominates, a brief quality-based explanation MAY be added:

> 本期最终作品较集中于 Pexels，原因是该平台在当前“马群 × 动态逆光”方向中的强候选质量明显高于其他来源，因此未为平台均衡牺牲作品质量。

Do not apologize for uneven platform distribution if the selection was quality-driven.

---

# 45. Discovery-Only Candidates

Some visually strong works may fail final verification.

Examples:

- Pinterest image cannot be traced;
- creator unknown;
- work page unavailable;
- licensing unclear;
- no legitimate download path;
- source appears to be a repost.

These works MAY influence:

- benchmark direction;
- search language;
- Aesthetic DNA;
- secondary discovery.

But they SHOULD NOT silently enter a final collection advertised as fully verified or downloadable.

---

# 46. Verified vs Reference-Only Works

Use clear distinctions when necessary.

Possible labels:

- **已核验作品**
- **视觉参考**
- **来源未完全核验**
- **仅作方向参考**

Never present a reference-only image as though it has complete source and download verification.

---

# 47. Partial Verification

If most metadata is verified but one field is missing, preserve the valid result.

Example:

- photograph verified;
- creator verified;
- work page verified;
- license verified;
- raw download URL unavailable.

Then deliver:

> 原图下载：可通过原作品页官方下载入口获取，本次未取得可独立核验的直接原图地址。

Do not downgrade the entire work unnecessarily.

---

# 48. Broken or Inaccessible Work Pages

If a previously identified work page becomes unavailable during the current run:

1. search for the same exact work through another authoritative source;
2. verify creator identity;
3. preserve the original source when possible;
4. replace the work if integrity cannot be maintained.

Do not silently substitute another photograph.

---

# 49. Duplicate Detection

Before final delivery, check that the nine selected works are actually distinct.

Avoid:

- duplicate uploads;
- cropped duplicates;
- mirrored duplicates;
- different resolutions of the same image;
- near-identical frames unintentionally selected as separate works.

Multiple photographs from the same sequence MAY be used only when each contributes a genuinely distinct visual role and the repetition is intentional.

---

# 50. Preview / Source / Download Consistency Check

Before final delivery, verify for every work:

`Preview = Listed Photograph = Work Page = Creator = Download Entry`

If any link in this chain is inconsistent:

- repair the mismatch;
- replace the work;
- or state the limitation.

Never knowingly deliver mismatched metadata.

---

# 51. Final Source Verification Checklist

Before presenting the collection, check:

## Discovery

- [ ] Multiple sources were genuinely searched when the host allowed it.
- [ ] No source was falsely reported as searched.
- [ ] Pinterest was treated primarily as discovery unless original source verification succeeded.

## Identity

- [ ] Every final work corresponds to the listed photograph.
- [ ] Creator information is verified where possible.
- [ ] Original title is preserved when available.
- [ ] Duplicate works are removed.

## Source

- [ ] Work page belongs to the exact photograph.
- [ ] URLs were not guessed or constructed.
- [ ] More authoritative sources were preferred over reposts where practical.

## License

- [ ] License claims are based on actual evidence.
- [ ] Commercial-use claims are not inferred from mere download availability.
- [ ] Work-specific Flickr licenses were checked where applicable.
- [ ] Meaningful restrictions are disclosed.

## Download

- [ ] Download entries correspond to the exact selected works.
- [ ] Raw file URLs were not fabricated.
- [ ] Thumbnails are not labeled as original downloads.

## Preview

- [ ] Direct previews correspond to the selected works.
- [ ] Similar images are not used as substitutes.
- [ ] AI-generated recreations are not presented as the original photographs.

---

# 52. Final Delivery Checklist

Before completing the response, check:

- [ ] Default output language is Simplified Chinese unless overridden.
- [ ] Artistic title is present.
- [ ] 1–3 sentence poetic introduction is present.
- [ ] Theme is clearly stated.
- [ ] Platforms actually searched are listed.
- [ ] Benchmark image is identified.
- [ ] Aesthetic DNA is summarized.
- [ ] Exactly 9 final works are delivered when real-image discovery is available and the user did not request another number.
- [ ] Direct previews are shown when the host reliably supports them.
- [ ] Every work has a Chinese display title.
- [ ] Every work has creator/source information where verifiable.
- [ ] Every work has concise curator commentary.
- [ ] Every work communicates a memory point.
- [ ] Every work communicates an Irreplaceable Point.
- [ ] Original work pages are included where verified.
- [ ] Download entries are included where verified.
- [ ] License information is accurate where provided.
- [ ] Platform composition is summarized.
- [ ] File/ZIP status is reported according to `files-and-fallback.md`.

---

# 53. User-Facing Output Template

For a standard full run, use a structure similar to:

```text
《系列艺术标题》

1–3句诗意短文案。

当期主题：……
实际搜索平台：……

基准图：……
核心审美 DNA：……

[九张最终作品直接预览，如宿主支持]

01_中文作品名.jpg｜XX分｜作者｜来源平台
原作品名：……

策展说明：……
记忆点：……
创意点：……
不可替代点：……

作品页面：……
原图下载：……
许可：……

02_……
……
09_……

本期平台构成：……

ZIP下载：……
```

The host MAY adapt formatting to its interface.

Do not omit essential information merely for cosmetic reasons.

---

# 54. Compact Delivery Principle

The final response should be visually rich but information-dense.

Avoid turning each image into a long essay.

The user should be able to:

1. view the collection;
2. understand why each work was selected;
3. identify the creator;
4. open the original source;
5. download the work when permitted;
6. understand the collection's aesthetic direction.

Curatorial explanation should support the photographs rather than overwhelm them.

---

# 55. Truthfulness Standard

When uncertain, prefer:

> “当前无法核验”

over:

> invented certainty.

When a capability fails, prefer:

> accurate partial delivery

over:

> fabricated completeness.

The quality of `Daily Photo Curator` depends not only on aesthetic judgment but also on whether every presented photograph can be trusted.

---

# 56. Final Standard

A successful source-and-delivery stage should allow the user to receive a collection that is:

- visually compelling;
- coherent;
- clearly attributed;
- traceable to real sources;
- transparent about licensing;
- easy to preview;
- easy to download when supported;
- consistent in format;
- honest about technical limitations.

The final experience should feel like:

> **AI 已经替用户完成了寻找、筛选、核验和整理，用户只需要看图、收藏和使用。**
