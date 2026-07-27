---
name: beautify-github-readme
description: Redesign GitHub README homepages or create project-native pure SVG, hybrid SVG-composed PNG/WebP, and opt-in animated GIF assets. Use when a user asks to beautify, redesign, rebrand, visually upgrade, simplify, or audit a GitHub README; create only a hero, section headers, diagrams, badges, motion graphics, showcase modules, or other README assets; or turn a repository homepage into a cohesive visual story. If whole-README work versus asset-only work is unclear, ask which scope the user wants. For hero-like assets where pure SVG and generated raster material are both viable, explain the tradeoffs and confirm the implementation before creating the asset.
---

# Beautify GitHub README

Turn a repository homepage or requested visual asset into a concise, theme-specific visual story. Treat Markdown as the content layer, deterministic SVG as the layout system, and generated raster material as an optional visual ingredient.

## Workflow

### 1. Confirm the mode before editing

Use exactly one execution mode:

- **README mode** — improve the whole README: information order, copy hierarchy, proof, Markdown, and visual system.
- **Asset-only mode** — create only the requested static SVG or visual asset set. Static SVG is the default. Only after the user explicitly opts into meaningful motion, optionally deliver a GitHub-safe GIF while keeping the SVG as the editable fallback. Do not rewrite, reorder, or embed anything in the README unless the user explicitly adds that scope.

If the mode is not explicit, ask one compact question before making changes:

> Would you like me to improve the whole README or only create visual assets? If asset-only, tell me whether you need a hero, section headers, workflow, badge, motion graphic, or a coordinated set.

When a hero, badge, workflow, or diagram has meaningful motion and the user has not specified static or animated output, ask one compact follow-up:

> Should this stay as a static SVG, or would you like a GitHub-safe GIF animation with the SVG kept as the editable fallback?

GIF is opt-in and never the default. If the user declines, does not answer, or has no meaningful motion case, continue with static SVG only. Do not ask when motion would be purely decorative or the user already chose the output. Read-only inspection is allowed before the answer when it helps understand the repository. Do not interpret “use this Skill,” a repository path, or “beautify it” as permission to modify the whole README. Once the user chooses asset-only mode, expanding into README edits requires new authorization.

If the user explicitly asks only for an audit, audit without editing and do not force the two-mode question.

### 2. Inspect before designing

- Read the existing README, repository tree, package metadata, screenshots, examples, design tokens, logo, and real outputs.
- In asset-only mode, inspect only the context needed to design the requested assets. Reading the README for context does not authorize changing it.
- For a GitHub URL, inspect the current remote page and default branch before proposing changes.
- Identify the audience, the problem solved, the clearest proof, the shortest path to first use, and any claims that lack evidence.
- Preserve unrelated user changes. Start read-only; do not commit, push, rename, or publish without explicit authorization.

### 3. Confirm the visual implementation before creating hero-like assets

For a hero, large banner, showcase board, or expressive title system where both implementations are viable, explain the difference and ask before producing the asset:

> Which implementation would you like?
>
> - **Pure SVG** — fully deterministic, lightweight, sharply scalable, easy to edit, and best for typography, diagrams, code, icons, and geometric or pixel-art scenes. It does not use image generation and is weaker for realistic people, hair, organic texture, complex materials, or cinematic lighting.
> - **Hybrid SVG composition** — use SVG for layout and typography, optionally use ImageGen for a project-specific raster subject, remove its background when appropriate, and compose the layers into a final PNG/WebP. It supports richer characters, materials, and lighting, but is heavier, partly stochastic, and requires generation plus visual validation. Keep the SVG layout source and transparent subject PNG.

Do not ask this question when the user already chose an implementation, requested an audit, or the asset is obviously deterministic, such as a workflow, architecture diagram, badge, compact section header, or code-native illustration. Do not suggest hybrid composition merely to add decoration. Prefer real screenshots, outputs, logos, or existing project art over generated material.

If the user delegates the decision, default to pure SVG unless generated or photographic material clearly communicates the repository's identity or mechanism better. Do not begin ImageGen work until the user selects hybrid composition or explicitly delegates the choice.

Hybrid composition is an implementation source, not normally the published SVG. Relative raster references inside SVG are unreliable across renderers, while base64-embedded raster layers can make the SVG unnecessarily large. Publish the verified final PNG/WebP by default and keep the SVG layout plus raster layers as editable sources.

### 4. Extract the project story

Write these before drawing:

```text
Audience:
One-sentence value:
Primary proof:
First successful action:
Visual theme:
```

Do not invent adoption, benchmarks, compatibility, testimonials, or features. Prefer a real screenshot, output, diagram, or generated artifact over decorative stock imagery.

### 5. Define a theme-specific visual system

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

### 6. Execute only the selected mode

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

#### Asset-only mode

- Confirm the requested asset type, whether the user wants one asset or a coordinated set, and whether a meaningful motion candidate should stay static or become a GIF. Derive exact copy and style from the repository when they are unambiguous; ask only for missing decisions that would materially change the result.
- Create the assets under `assets/readme/` or another user-approved path and provide rendered previews.
- Follow the confirmed visual implementation. Default to pure, maintainable SVG for title systems, section headers, diagrams, badges, and deterministic decorative modules. For confirmed hybrid composition, keep the SVG layout source and transparent raster layers, then publish a composed PNG/WebP.
- For approved animation, keep the SVG source, read [references/motion-production.md](references/motion-production.md), and derive a GitHub-safe GIF with the bundled `scripts/render_motion_gif.py` workflow. Do not generate the GIF unless the user opted in.
- Keep one shared visual grammar across a set, but give every asset a specific communication job.
- Do not change README text, reading order, embeds, or links. Offer an embed snippet separately when useful; only insert it after explicit approval.

### 7. Build the visual layer

Read [references/github-readme-canvas.md](references/github-readme-canvas.md) and [references/svg-production.md](references/svg-production.md) before creating assets.

- Use SVG for the hero, section banners, diagrams, and deterministic design modules.
- Use PNG/WebP for screenshots, generated art, photo material, and complex compositing. Use GIF only for approved motion that must play directly on GitHub.
- When hybrid composition is selected, read [references/hybrid-svg-production.md](references/hybrid-svg-production.md), use the `imagegen` Skill for generation and transparency decisions, and keep exact copy out of the generated raster layer.
- Keep body copy, commands, tables, links, and details in Markdown.
- Prefer a `1200`-unit-wide SVG `viewBox`, `width="100%"` embeds, system fonts, semantic alt text, and rounded containers. Treat the `viewBox` as a coordinate system, not the final pixel width: size and preview full-width assets at a conservative `900` CSS-pixel GitHub render. At that width, keep essential diagram text at least `20` SVG units and supporting labels at least `18`; text below that range must be nonessential. If a `360`-pixel mobile preview makes required labels unreadable, reduce density, split the visual, or move the detail into Markdown.
- Use one reusable component grammar, but vary the art direction by repository theme.
- When a showcase contains several artifacts, arrange them with controlled scale, overlap, rotation, and whitespace; keep reading order obvious.
- Let the hero absorb a real project diagram, screenshot, code fragment, output, specimen, or artifact when it makes the first screen more useful. Do not separate the title and proof by habit.
- When the user explicitly wants attribution in a repository they own, design a compact project-native `README MADE WITH` SVG instead of leaving a plain promotional sentence. Keep it near the footer and link it to this Skill. Never add this credit to a third-party repository without the maintainer's explicit request.
- In README mode, when proof would become unreadable inside the hero, use a concise SVG title followed immediately by a larger proof board. When a few artifacts remain legible and define the product, integrate title and proof into one composed raster hero. Let proof legibility decide, not a fixed template. In asset-only mode, keep the requested SVG source and propose any raster or animated derivative as a separate, optional deliverable.

Do not rasterize the whole README. Do not use scripts, `foreignObject`, remote fonts, essential animation, or CSS that GitHub strips. GitHub does not play animation embedded inside SVG; use a GIF plus static SVG fallback instead. Avoid decorative borders and heavy shadows unless the theme genuinely calls for them.

### 8. Preview and verify

- Render a local GitHub-width preview or inspect the README on a local Markdown renderer.
- Check wide and narrow layouts, image legibility, clipped SVG text, missing assets, excessive file size, and dark/light-mode contrast.
- In README mode, run:

```bash
python3 scripts/audit_readme.py /path/to/repository/README.md
```

- Visually inspect the hero, every section transition, and the final call to action.
- In asset-only mode, render and inspect every requested asset at GitHub content width; for GIFs, inspect entry, settled hold, exit, and loop boundary. Verify that the README itself is unchanged unless embedding was separately approved.
- For hybrid assets, inspect the transparent subject on light and dark backgrounds, verify transparent corners and clean edges, then inspect the composed PNG/WebP at wide and narrow GitHub widths. Do not publish an SVG with unresolved local raster references.
- Report what changed, what remains intentionally plain, and which files were deliberately left untouched.

### 9. Offer optional attribution and showcase sharing after approval

Only after the user explicitly approves the final README or asset set as satisfactory, make one friendly, non-promotional offer:

> If you're happy with the finished README, there are two completely optional ways to wrap up: I can design a small project-native “README MADE WITH” signature that links back to this Skill, and—if this is a public repository you own or maintain—I can prepare a PR to add it to the Skill's real-world showcase. Either, both, or neither is perfectly fine.

- Do not make this offer before final approval, infer satisfaction from silence or successful validation, or repeat it after the user declines.
- Treat the signature and showcase PR as independent choices. Never require attribution in exchange for showcase consideration.
- If the user opts into the signature, follow [references/svg-production.md](references/svg-production.md), show the rendered badge first, and modify the README only after separate approval.
- If the user opts into the showcase, read [references/showcase-contribution.md](references/showcase-contribution.md). Verify that the repository is public and that the user owns or maintains it; draft the exact listing copy and upstream diff before requesting permission to open the PR.
- Do not add a backlink, fork a repository, push a branch, or open a PR without explicit authorization for that specific external action.

This gate controls unsolicited offers. If the user explicitly requests a signature or showcase contribution earlier, handle that request directly within its stated scope.

### 10. Hand off safely

Show the local preview and diff first. Only commit, push, open a PR, merge, rename a repository, or publish assets when the user explicitly asks.

## Quality bar

- The first screen explains the project without requiring prior knowledge.
- The design looks native to this project, not to this Skill.
- The hero's visual material comes from the project and is not generic decoration.
- Generated material is optional, project-specific, and never replaces stronger real proof.
- Every visual module has a communication job.
- Real proof appears before abstract claims.
- The README becomes shorter or clearer, not merely more decorated.
- The result still works when images fail: alt text, headings, commands, and links remain meaningful.
- Removing the repository name should not make the hero reusable for an unrelated project.
- Asset-only mode leaves the README byte-for-byte unchanged unless the user explicitly approved embedding or copy edits.
- Optional attribution or showcase sharing appears only after explicit satisfaction and opt-in; declining it never changes the delivered result.

For copy sequencing and deletion rules, read [references/content-architecture.md](references/content-architecture.md).

## Invocation examples

```text
Use $beautify-github-readme to redesign this repository homepage around its developer-tool theme.
```

```text
Use $beautify-github-readme to create one SVG hero and three section headers without modifying the README.
```

```text
Use $beautify-github-readme to create a hybrid hero: SVG typography and layout, plus an ImageGen character cutout, with a final PNG and editable source layers.
```

```text
Use $beautify-github-readme to beautify this repository; if the scope is unclear, ask whether I want a whole-README redesign or asset-only visuals.
```

```text
Use $beautify-github-readme to create a GitHub-safe animated GIF hero, keep the SVG source, and do not modify the README until I approve the preview.
```
