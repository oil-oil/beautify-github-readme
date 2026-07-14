---
name: beautify-github-readme
description: Redesign GitHub README homepages or create standalone GitHub-safe SVG decorations around a repository's real theme. Use when a user asks to beautify, redesign, rebrand, visually upgrade, simplify, or audit a GitHub README; create only an SVG hero, section headers, diagrams, badges, showcase modules, or other README assets; or turn a repository homepage into a cohesive visual story. If the request does not clearly distinguish whole-README work from asset-only SVG work, ask which scope the user wants before editing anything.
---

# Beautify GitHub README

Turn a repository homepage or a requested SVG asset into a concise, theme-specific visual story. Treat SVG as the visual layer and Markdown as the content layer.

## Workflow

### 1. Confirm the mode before editing

Use exactly one execution mode:

- **README mode** — improve the whole README: information order, copy hierarchy, proof, Markdown, and visual system.
- **SVG-only mode** — create only the requested SVG decoration or asset set. Do not rewrite, reorder, or embed anything in the README unless the user explicitly adds that scope.

If the mode is not explicit, ask one compact question before making changes:

> Would you like me to improve the whole README or only create SVG decorations? If SVG-only, tell me whether you need a hero, section headers, workflow, badge, or a coordinated visual set.

Read-only inspection is allowed before the answer when it helps understand the repository. Do not interpret “use this Skill,” a repository path, or “beautify it” as permission to modify the whole README. Once the user chooses SVG-only mode, expanding into README edits requires new authorization.

If the user explicitly asks only for an audit, audit without editing and do not force the two-mode question.

### 2. Inspect before designing

- Read the existing README, repository tree, package metadata, screenshots, examples, design tokens, logo, and real outputs.
- In SVG-only mode, inspect only the context needed to design the requested assets. Reading the README for context does not authorize changing it.
- For a GitHub URL, inspect the current remote page and default branch before proposing changes.
- Identify the audience, the problem solved, the clearest proof, the shortest path to first use, and any claims that lack evidence.
- Preserve unrelated user changes. Start read-only; do not commit, push, rename, or publish without explicit authorization.

### 3. Extract the project story

Write these before drawing:

```text
Audience:
One-sentence value:
Primary proof:
First successful action:
Visual theme:
```

Do not invent adoption, benchmarks, compatibility, testimonials, or features. Prefer a real screenshot, output, diagram, or generated artifact over decorative stock imagery.

### 4. Define a theme-specific visual system

Read [references/visual-direction.md](references/visual-direction.md). Freeze a compact art-direction spec:

```text
Palette: background / foreground / primary / accent / muted
Typography: system font stack / scale / weight contrast
Shape: radius / stroke / grid / spacing
Motif: one recurring project-specific visual cue
Composition: calm / editorial / technical / playful / cinematic
```

Derive the motif from the project. A terminal tool may use prompts and cursor marks; an icon system may use keylines and cutouts; a research project may use coordinates and evidence labels. Never apply the same yellow-grid template to every repository.

Before designing the hero, read [references/project-native-hero.md](references/project-native-hero.md). Build the title from project content rather than treating it as a banner placed above the proof. Choose the typography, composition, and right-side material from the repository itself.

### 5. Execute only the selected mode

#### README mode

Decide how deeply the README needs to change:

- **Full redesign** — restructure the story and build a new visual system.
- **Visual refresh** — preserve the information architecture while replacing weak or inconsistent presentation.

Use the smallest change inside README mode that can produce a meaningful improvement. Rebuild the reading order only when the selected scope requires it. A strong default is:

1. Hero: name + plain-language value.
2. Proof: screenshots, outputs, or a showcase wall.
3. What it is: one short explanation.
4. Why it is different: mechanism, not slogans.
5. How it works: a short process or architecture.
6. How to use: install + first command.
7. Limits, compatibility, license, or contribution details when relevant.

Put the example before the long explanation. Remove repeated promises and internal implementation detail that does not help adoption.

#### SVG-only mode

- Confirm the requested asset type and whether the user wants one asset or a coordinated set. Derive exact copy and style from the repository when they are unambiguous; ask only for missing decisions that would materially change the result.
- Create the assets under `assets/readme/` or another user-approved path and provide rendered previews.
- Default to pure, maintainable SVG for title systems, section headers, diagrams, badges, and deterministic decorative modules.
- Keep one shared visual grammar across a set, but give every asset a specific communication job.
- Do not change README text, reading order, embeds, or links. Offer an embed snippet separately when useful; only insert it after explicit approval.

### 6. Build the visual layer

Read [references/github-readme-canvas.md](references/github-readme-canvas.md) and [references/svg-production.md](references/svg-production.md) before creating assets.

- Use SVG for the hero, section banners, diagrams, and deterministic design modules.
- Use PNG/WebP for screenshots, generated art, photo material, and complex compositing.
- Keep body copy, commands, tables, links, and details in Markdown.
- Prefer a `1200`-wide SVG `viewBox`, `width="100%"` embeds, system fonts, semantic alt text, and rounded containers.
- Use one reusable component grammar, but vary the art direction by repository theme.
- When a showcase contains several artifacts, arrange them with controlled scale, overlap, rotation, and whitespace; keep reading order obvious.
- Let the hero absorb a real project diagram, screenshot, code fragment, output, specimen, or artifact when it makes the first screen more useful. Do not separate the title and proof by habit.
- When the user explicitly wants attribution in a repository they own, design a compact project-native `README MADE WITH` SVG instead of leaving a plain promotional sentence. Keep it near the footer and link it to this Skill. Never add this credit to a third-party repository without the maintainer's explicit request.
- In README mode, when proof would become unreadable inside the hero, use a concise SVG title followed immediately by a larger proof board. When a few artifacts remain legible and define the product, integrate title and proof into one composed raster hero. Let proof legibility decide, not a fixed template. In SVG-only mode, keep the requested output vector and propose any raster proof as a separate, optional deliverable.

Do not rasterize the whole README. Do not use scripts, `foreignObject`, remote fonts, essential animation, or CSS that GitHub strips. Avoid decorative borders and heavy shadows unless the theme genuinely calls for them.

### 7. Preview and verify

- Render a local GitHub-width preview or inspect the README on a local Markdown renderer.
- Check wide and narrow layouts, image legibility, clipped SVG text, missing assets, excessive file size, and dark/light-mode contrast.
- In README mode, run:

```bash
python3 scripts/audit_readme.py /path/to/repository/README.md
```

- Visually inspect the hero, every section transition, and the final call to action.
- In SVG-only mode, render and inspect every requested asset at GitHub content width; verify that the README itself is unchanged.
- Report what changed, what remains intentionally plain, and which files were deliberately left untouched.

### 8. Hand off safely

Show the local preview and diff first. Only commit, push, open a PR, merge, rename a repository, or publish assets when the user explicitly asks.

## Quality bar

- The first screen explains the project without requiring prior knowledge.
- The design looks native to this project, not to this Skill.
- The hero's visual material comes from the project and is not generic decoration.
- Every visual module has a communication job.
- Real proof appears before abstract claims.
- The README becomes shorter or clearer, not merely more decorated.
- The result still works when images fail: alt text, headings, commands, and links remain meaningful.
- Removing the repository name should not make the hero reusable for an unrelated project.
- SVG-only mode leaves the README byte-for-byte unchanged unless the user explicitly approved embedding or copy edits.

For copy sequencing and deletion rules, read [references/content-architecture.md](references/content-architecture.md).

## Invocation examples

```text
Use $beautify-github-readme to redesign this repository homepage around its developer-tool theme.
```

```text
Use $beautify-github-readme to create one SVG hero and three section headers without modifying the README.
```

```text
Use $beautify-github-readme to beautify this repository; if the scope is unclear, ask whether I want a whole-README redesign or SVG-only assets.
```
