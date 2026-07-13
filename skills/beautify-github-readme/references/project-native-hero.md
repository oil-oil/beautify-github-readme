# Project-native hero

Design the README title from the repository's actual content. Do not place a generic banner above a separate screenshot by default.

## Start from five facts

Write these before opening the SVG:

```text
Project category:
Main user:
Main action:
Best proof:
Native visual material:
```

Native visual material is the thing the project really works with: cluster relationships, tensors, tables, code, layers, timelines, maps, icons, terminal output, or generated artifacts.

## Use a stable information anatomy

A useful title can contain five parts:

1. Category or technical context.
2. Repository name.
3. One concrete description.
4. Real project material.
5. Small repository metadata.

Keep the anatomy stable enough to communicate clearly, but move, resize, or omit parts to suit the project. Do not turn it into one fixed template.

## Choose typography from the project

| Project character | Useful type direction |
| --- | --- |
| Infrastructure / systems | large sans-serif + mono metadata |
| Research / database | sober serif or restrained sans-serif + measured diagrams |
| Programming language / low-level tool | industrial display type + code mono |
| Creative tool / design system | open sans-serif or expressive display type + specimens |
| Documentation / knowledge project | quiet readable type + editorial hierarchy |

Use type to express how the project speaks. Do not use serif merely to look premium or monospace merely to look technical.

## Choose a composition mode

- **Split** — title on one side, project structure or artifact on the other. Use when the project has one clear visual proof.
- **Integrated** — let diagrams, paths, code, screenshots, or specimens share the same grid as the title. Use when content and identity are inseparable.
- **Artifact wall** — place several real outputs on a controlled diagonal and let the title occupy one cell or the negative space between them.
- **Background proof** — enlarge one real artifact behind or around the title. Use only when contrast remains clear.
- **Title-only** — use typography and spacing alone when the project is intentionally minimal and has no honest visual proof.

Do not force every repository into a left-title/right-graphic split. Choose the mode after seeing the material.

## Combine title and demonstration

When the first screenshot, output, or diagram explains the project, combine it with the title into one composition:

```text
category + repository name + concrete description + real proof
```

For vector material, keep the whole composition in SVG. For screenshots, photos, or generated raster work, compose the title and images in a layout tool or HTML canvas and export one PNG/WebP. Do not rely on fragile external image links inside SVG.

## Use project-specific tests

Before accepting the hero, ask:

1. If the repository name disappears, could this hero belong to an unrelated project?
2. Does the visual material explain the project, or does it only make the page look technical?
3. Can a first-time visitor tell what the repository does without reading the body?
4. Does the typography fit the project's character and audience?
5. Could the title and proof be composed more tightly instead of appearing as two unrelated blocks?

If the first answer is yes or the second answer is decoration, redesign it.

## Example translations

- Kubernetes: cluster relationships, production scheduling, strict black system layout.
- PyTorch: tensor or network paths, open research spacing, orange computational flow.
- PostgreSQL: tables and relationships, stable deep blue, serif or measured database typography.
- Rust: code structure, industrial display type, strong separation between language and example.
- Icon system: keylines, 4×4 sheets, transparent outputs, cropped specimens.

Use the examples as reasoning patterns, not as templates to copy.
