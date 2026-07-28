<p align="right">
  <strong>English</strong> · <a href="./README.zh-CN.md">简体中文</a> · <a href="./README.ja.md">日本語</a>
</p>

<p align="center">
  <img src="./assets/readme/en/hero.gif" width="100%" alt="Beautify GitHub README: help visitors understand a repository at first glance.">
</p>

<p align="center">
  <img src="./assets/readme/en/theme-wall.svg" width="100%" alt="Six project-native README directions for developer tools, AI products, design resources, research, creator projects, and open-source libraries.">
</p>

<p align="center">
  <img src="./assets/readme/en/section-used-by.svg" width="100%" alt="Real repositories already using beautify-github-readme.">
</p>

These are not hypothetical templates. The method is already used by nine public repositories, each with its own visual language and content structure:

- **[oil-ppt](https://github.com/oil-oil/oil-ppt)** — presents the method, results, and first-use path for programmatic slide creation in one visual system.
- **[draw-ui](https://github.com/oil-oil/draw-ui)** — uses real UI outputs to explain the path from a brief and reference images to HTML/CSS reconstruction.
- **[oil-icon](https://github.com/oil-oil/oil-icon)** — uses real icon sets to explain style locking, batch generation, slicing, and transparent delivery.
- **[Selector](https://github.com/oil-oil/selector)** — puts page selection, structured context, and real output directly into the opening screen and examples.
- **[codex-dev-team](https://github.com/oil-oil/codex-dev-team)** — uses a character-driven team map to explain how one main Codex thread delegates exploration, bounded implementation, and independent review to four custom agents.
- **[torqueDASH-Next](https://github.com/moesix/torque-dash-next)** — uses a project-native SVG hero with OBD-II PID data and a real dashboard screenshot to explain a self-hosted vehicle telemetry dashboard.
- **[summertown](https://github.com/SummerPapaya/summertown)** — uses a seaside-map hero and landmark showcase to introduce an interactive town map.
- **[Wolfcha](https://github.com/oil-oil/wolfcha)** — combines SVG typography and an AI-generated character cutout to turn “play Werewolf solo” into a cinematic, project-native opening screen.
- **[wecom-qoder-bridge](https://github.com/painrice/wecom-qoder-bridge)** — uses a terminal-mock hero and a five-node system map to expose a local qoderclicn agent behind a WeCom smart bot without needing a public domain.

If this Skill helped you create a public README you are proud of, you are welcome to propose it for this list in a PR. This is completely optional: the footer signature is appreciated but never required, and showcase submissions remain subject to maintainer review.

Below are four independent hero directions. They do not share one house style; each derives its typography, color, composition, and proof from the project itself.

<p align="center">
  <img src="./assets/readme/en/case-kubernetes.svg" width="100%" alt="Kubernetes README hero example with a black system layout and cluster relationship diagram.">
</p>

<p align="center">
  <img src="./assets/readme/en/case-postgresql.svg" width="100%" alt="PostgreSQL README hero example with a deep blue editorial layout and relational tables.">
</p>

<p align="center">
  <img src="./assets/readme/en/case-block-world.png" width="100%" alt="Block World hybrid README hero combining pixel-style SVG composition with an AI-generated builder character cutout.">
</p>

**Block World** shows a playful hybrid direction: SVG builds the pixel typography, grid, labels, and scene structure, while ImageGen and chroma-key removal supply the character that would be cumbersome to draw deterministically.

<p align="center">
  <a href="https://github.com/oil-oil/wolfcha">
    <img src="./assets/readme/en/case-wolfcha.png" width="100%" alt="Wolfcha hybrid README hero combining precise SVG typography and table graphics with an AI-generated wolf game master.">
  </a>
</p>

**[Wolfcha](https://github.com/oil-oil/wolfcha)** is a real hybrid case: ImageGen created the project-specific wolf game master, a fixed chroma-key workflow removed the background, and SVG kept the typography, moonlit table, seat map, and composition precise.

<p align="center">
  <img src="./assets/readme/en/section-why.svg" width="100%" alt="01 Make the project clear before asking people to keep reading.">
</p>

Most repositories already contain enough information. The problem is usually the order: visitors see internal terminology, installation commands, and directory trees before they understand what the project is for.

`beautify-github-readme` reads the real repository first, identifies the clearest value and proof, and only then decides how the page should look.

<p align="center">
  <img src="./assets/readme/en/before-after.svg" width="100%" alt="A README changing from dense information with no clear entry point to a value, proof, method, and first-use sequence.">
</p>

In whole-README mode, it works across three layers:

| Content | Visual system | Engineering |
| --- | --- | --- |
| Remove repetition, move proof forward, and replace internal jargon with concrete outcomes | Derive color, typography, composition, and project-native motifs before designing the hero and supporting modules | Keep assets GitHub-safe, images accessible, commands copyable, and body text searchable |

Different projects should not receive the same template. A CLI can use command rhythm and cursors; an icon system can use keylines and cutouts; a research repository can use coordinates, charts, and evidence labels.

<p align="center">
  <img src="./assets/readme/en/section-method.svg" width="100%" alt="02 Put visual identity in SVG and readable content in Markdown.">
</p>

GitHub READMEs do not have the layout freedom of a website. This Skill separates the visual and content layers:

- SVG handles editable heroes, section transitions, comparisons, diagrams, and identity.
- Hybrid SVG composition combines deterministic SVG layout with optional AI-generated, background-removed subjects for characters, organic texture, complex materials, and cinematic lighting.
- GIF handles approved motion while the static SVG remains the editable fallback.
- Motion is opt-in and is never generated by default.
- PNG/WebP handles screenshots, generated artwork, and complex showcase walls.
- Markdown handles explanations, commands, links, configuration, and contribution details.

The result can feel designed without becoming one long image that nobody can search, copy, or maintain.

The reusable production guidance lives here:

- [Designing a project-native hero](./skills/beautify-github-readme/references/project-native-hero.md)
- [Writing GitHub-safe README SVGs](./skills/beautify-github-readme/references/svg-production.md)
- [Composing SVG with generated raster material](./skills/beautify-github-readme/references/hybrid-svg-production.md)
- [Producing GitHub-safe README motion](./skills/beautify-github-readme/references/motion-production.md)

<p align="center">
  <img src="./assets/readme/en/workflow.svg" width="100%" alt="Understand the project, set the direction, structure the content, build the visuals, and review the preview.">
</p>

The process keeps three promises: use real project material, never invent capabilities, and never publish without explicit approval.

<p align="center">
  <img src="./assets/readme/en/section-use.svg" width="100%" alt="03 Send the repository to your Agent.">
</p>

**Option 1 · Install from the command line**

```bash
npx skills add oil-oil/beautify-github-readme
```

**Option 2 · Ask your Agent to install it**

```text
Install this Skill: https://github.com/oil-oil/beautify-github-readme
```

The Skill has two explicit modes:

| Mode | What it changes | What it leaves alone by default |
| --- | --- | --- |
| Whole README | Reading order, copy hierarchy, proof, Markdown, and the complete visual system | It will not commit, push, or publish without approval |
| Asset-only | A static SVG hero, section headers, workflow, badge, diagram, or an optional GitHub-safe GIF with SVG source | It will not edit README copy, order, image references, or links |

If the request already states the scope, the Skill starts directly. If a user only says “beautify this repository” or provides a repository URL, the Agent asks:

```text
Would you like me to improve the whole README or only create visual assets?
If asset-only, do you need a hero, section headers, workflow, badge, motion graphic, or a coordinated set?
```

**Whole-README mode**

```text
Use $beautify-github-readme to redesign this repository homepage around its real project theme.
Show me a local preview first and do not push anything.
```

**Asset-only mode**

```text
Use $beautify-github-readme to keep the README unchanged and create one animated GIF hero with its SVG source.
Derive the style from the existing project and show me the rendered preview first.
```

Reading a README for context does not grant permission to edit it. In asset-only mode, embedding the new assets requires a separate, explicit approval.

You can also request a read-only audit:

```text
Use $beautify-github-readme to audit this README for clarity, hierarchy, trust, and maintenance cost. Do not edit files.
```

Whole-README mode delivers a local preview, visual assets, and a README diff. Asset-only mode delivers source assets, rendered previews, optional GIF derivatives, and embed snippets. Commits, pushes, PRs, and publishing always require explicit authorization.

<p align="center">
  <a href="https://x.com/I_am_oil_oil"><img src="./assets/readme/follow-on-x.svg" width="420" alt="Follow the maker on X at @I_am_oil_oil"></a>
</p>

MIT License

---

This README is also a working example: it combines a project-native hero, a theme wall, real adoption proof, section transitions, and readable Markdown instead of rasterizing the whole page.
