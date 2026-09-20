<p align="right">
  <a href="./README.zh-CN.md">简体中文</a> · <a href="./README.ja.md">日本語</a>
</p>

# beautify-github-readme

An Agent Skill that turns a repository homepage into a short visual story built from the project's own material — real screenshots, outputs, diagrams, and code — instead of a generic template.

```bash
npx skills add oil-oil/beautify-github-readme
```

Then tell your agent which scope you want (it will ask if you don't):

```text
Use $beautify-github-readme to redesign this repository homepage around its real project theme.
Show me a local preview first and do not push anything.
```

## Which job do you want?

| You say | The Skill does | It never does without extra approval |
| --- | --- | --- |
| "Redesign the whole README" | Reorders content, rewrites hierarchy, rebuilds the visual system, shows a local preview + diff | Commit, push, open a PR, or publish |
| "Just make assets" | Creates SVG heroes, headers, diagrams, badges (or an opt-in GIF with SVG source) under `assets/readme/` | Touch README text, order, embeds, or links |
| "Audit only" | Reports on clarity, hierarchy, trust, and maintenance cost | Edit any file |

Reading your README for context is not permission to change it.

## Proof, not promises

Eight public repositories already ship homepages built this way. None of them share a house style — each keeps its own typography, color, and proof:

| Repository | What the homepage proves first |
| --- | --- |
| [oil-ppt](https://github.com/oil-oil/oil-ppt) | Method, results, and first-use path for programmatic slides in one visual system |
| [draw-ui](https://github.com/oil-oil/draw-ui) | Real UI outputs tracing brief → reference → HTML/CSS reconstruction |
| [oil-icon](https://github.com/oil-oil/oil-icon) | Style locking, batch generation, slicing, and transparent delivery on real icon sets |
| [Selector](https://github.com/oil-oil/selector) | Page selection, structured context, and real output on the opening screen |
| [codex-dev-team](https://github.com/oil-oil/codex-dev-team) | A character-driven team map: one main Codex thread delegating to four agents |
| [torqueDASH-Next](https://github.com/moesix/torque-dash-next) | OBD-II PID data + a real dashboard screenshot for a self-hosted vehicle telemetry dashboard |
| [summertown](https://github.com/SummerPapaya/summertown) | A seaside-map hero introducing an interactive town map |
| [Wolfcha](https://github.com/oil-oil/wolfcha) | An AI-generated wolf game master fused with precise SVG typography for solo Werewolf play |

Proud of a public README this Skill helped you make? Proposing it for this table via PR is welcome and entirely optional — no footer signature required.

## How a run goes

1. **Inspect** — README, tree, metadata, screenshots, examples, tokens, real outputs. Nothing invented: no fake adoption, benchmarks, or endorsements.
2. **Summarize the story in five lines** — audience, one-sentence value, primary proof, first successful action, visual theme.
3. **Freeze the art direction** — palette, type, shape, one project-derived motif, composition. A CLI gets prompts and cursors; an icon set gets keylines; research gets coordinates — never one template for all.
4. **Build in the confirmed scope** — whole README, or assets only.
5. **Preview and verify** — local GitHub-width render, narrow-layout check, link/asset audit, explicit approval before anything is committed or published.

## The layer contract

- **Markdown** owns words: explanations, commands, links, config. Searchable and copyable, always.
- **SVG** owns layout: heroes, section transitions, comparisons, diagrams. Deterministic, editable, `1200`-unit viewBox, system fonts.
- **PNG/WebP** owns captures: screenshots, generated art, showcase walls.
- **GIF** owns motion — opt-in only, never by default, with the static SVG kept as fallback.
- **Hybrid composition** (SVG layout + background-removed generated subject → final PNG/WebP) is offered only when both implementations fit, and confirmed before any generation starts.

The full production rules live in [`skills/beautify-github-readme/references/`](./skills/beautify-github-readme/references/): hero direction, SVG safety, hybrid compositing, motion, canvas, content architecture, visual direction, showcase rules. Two runnable scripts ship alongside: [`audit_readme.py`](./skills/beautify-github-readme/scripts/audit_readme.py) (image refs + SVG safety) and [`render_motion_gif.py`](./skills/beautify-github-readme/scripts/render_motion_gif.py) (GitHub-safe GIF workflow). Agent metadata: [`agents/openai.yaml`](./skills/beautify-github-readme/agents/openai.yaml).

## What it will not do

- Commit, push, PR, merge, rename, or publish without your explicit ask.
- Expand an asset-only job into README edits (that needs a new approval).
- Generate motion, characters, or photographic material unprompted.
- Rasterize the whole page into one unsearchable image.
- Use `foreignObject`, remote fonts, scripts, or CSS GitHub strips.

## Asset catalog

Previously published visuals are kept as sources under [`assets/readme/`](./assets/readme/): hero SVG + GIF + motion spec, theme wall, before/after comparison, workflow diagram, section transitions, four hero case studies (Kubernetes, PostgreSQL, Block World, Wolfcha), and the follow-on-X mark. This page deliberately embeds none of them — it is pure Markdown, and that is the point: design should survive with images turned off.

## Prompts you can copy

Audit (read-only):

```text
Use $beautify-github-readme to audit this README for clarity, hierarchy, trust, and maintenance cost. Do not edit files.
```

Whole README:

```text
Use $beautify-github-readme to redesign this repository homepage around its real project theme.
Show me a local preview first and do not push anything.
```

One animated hero, README untouched:

```text
Use $beautify-github-readme to keep the README unchanged and create one animated GIF hero with its SVG source.
Derive the style from the existing project and show me the rendered preview first.
```

## FAQ

**Will it match my project's look, or apply a house style?**
Your project's. The motif, palette, and composition are derived from your repo; "not reusable for an unrelated project" is an explicit quality gate.

**Where does AI-generated imagery fit?**
Nowhere by default. Hybrid composition is proposed only when generated material communicates identity or mechanism better than real proof — and only after you confirm.

**Why is this page so plain?**
Deliberately. The old page embedded a dozen full-width visuals; this one links them as a catalog. If a README about READMEs can't survive as text, the method is decoration.

## License and author

MIT License. Made by [@I_am_oil_oil](https://x.com/I_am_oil_oil).

---
*English is the source of truth; [简体中文](./README.zh-CN.md) and [日本語](./README.ja.md) translations may lag behind.*
