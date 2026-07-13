---
name: beautify-github-readme
description: Redesign and polish GitHub repository README homepages around the real project theme. Use when a user asks to beautify, decorate, redesign, rebrand, visually upgrade, or simplify a GitHub README; create SVG hero banners, section headers, showcase walls, before/after modules, or a cohesive repository homepage; or make a README feel like a designed landing page while keeping it readable and maintainable.
---

# Beautify GitHub README

Turn a repository homepage into a concise, theme-specific visual story. Treat SVG as the visual layer and Markdown as the content layer.

## Workflow

### 1. Inspect before designing

- Read the existing README, repository tree, package metadata, screenshots, examples, design tokens, logo, and real outputs.
- For a GitHub URL, inspect the current remote page and default branch before proposing changes.
- Identify the audience, the problem solved, the clearest proof, the shortest path to first use, and any claims that lack evidence.
- Preserve unrelated user changes. Start read-only; do not commit, push, rename, or publish without explicit authorization.

### 2. Choose the scope

Classify the request:

- **Full redesign** — restructure the story and build a new visual system.
- **Visual refresh** — keep the information architecture; replace weak or inconsistent presentation.
- **Audit** — diagnose hierarchy, clarity, trust, visual rhythm, and maintenance cost without editing.

If the user did not specify, infer the smallest scope that can produce a meaningful improvement.

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

### 5. Rebuild the reading order

Use the smallest useful structure. A strong default is:

1. Hero: name + plain-language value.
2. Proof: screenshots, outputs, or a showcase wall.
3. What it is: one short explanation.
4. Why it is different: mechanism, not slogans.
5. How it works: a short process or architecture.
6. How to use: install + first command.
7. Limits, compatibility, license, or contribution details when relevant.

Put the example before the long explanation. Remove repeated promises and internal implementation detail that does not help adoption.

### 6. Build the visual layer

Read [references/github-readme-canvas.md](references/github-readme-canvas.md) and [references/svg-production.md](references/svg-production.md) before creating assets.

- Use SVG for the hero, section banners, diagrams, and deterministic design modules.
- Use PNG/WebP for screenshots, generated art, photo material, and complex compositing.
- Keep body copy, commands, tables, links, and details in Markdown.
- Prefer a `1200`-wide SVG `viewBox`, `width="100%"` embeds, system fonts, semantic alt text, and rounded containers.
- Use one reusable component grammar, but vary the art direction by repository theme.
- When a showcase contains several artifacts, arrange them with controlled scale, overlap, rotation, and whitespace; keep reading order obvious.
- Let the hero absorb a real project diagram, screenshot, code fragment, output, specimen, or artifact when it makes the first screen more useful. Do not separate the title and proof by habit.

Do not rasterize the whole README. Do not use scripts, `foreignObject`, remote fonts, essential animation, or CSS that GitHub strips. Avoid decorative borders and heavy shadows unless the theme genuinely calls for them.

### 7. Preview and verify

- Render a local GitHub-width preview or inspect the README on a local Markdown renderer.
- Check wide and narrow layouts, image legibility, clipped SVG text, missing assets, excessive file size, and dark/light-mode contrast.
- Run:

```bash
python3 scripts/audit_readme.py /path/to/repository/README.md
```

- Visually inspect the hero, every section transition, and the final call to action.
- Report what changed and what remains intentionally plain.

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

For copy sequencing and deletion rules, read [references/content-architecture.md](references/content-architecture.md).

## Invocation examples

```text
Use $beautify-github-readme to redesign this repository homepage around its developer-tool theme.
```

```text
用 $beautify-github-readme 美化这个仓库，先给我本地预览，不要推送。
```
