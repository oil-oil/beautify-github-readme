# Hybrid SVG composition

Use hybrid composition when deterministic SVG layout needs raster material that SVG cannot express honestly: people, mascots, organic texture, complex surfaces, cinematic lighting, or generated project artifacts.

Do not use it when a real screenshot, output, logo, or repository-native illustration communicates the project better. Do not add a generic character merely to make the README look polished.

## Output contract

Treat SVG as the editable composition source and PNG/WebP as the published README asset:

```text
assets/readme/
├── hero.png                 # or hero.webp; publish this
└── source/
    ├── hero-layout.svg      # deterministic layout
    ├── hero-subject.png     # transparent raster layer
    └── hero-prompt.txt      # final generation prompt
```

Keep chroma-key source images in a temporary project folder during production. Remove discarded or intermediate files before handoff unless the user requests them.

Do not publish an SVG that depends on absolute paths, unresolved relative raster references, or remote images. Do not base64-embed a large raster layer merely to preserve an `.svg` extension. If the user explicitly wants a self-contained hybrid SVG, explain the file-size and renderer-compatibility tradeoff, then verify the actual GitHub rendering before using it.

## Production sequence

1. Freeze the repository story and visual system before generation.
2. Define the raster subject's communication job. Write why it belongs to this project.
3. Build the SVG layout first with a clearly reserved subject area.
4. Invoke the `imagegen` Skill. Keep title text, body copy, labels, logos, and UI chrome out of the generated layer.
5. Generate the subject with its pose, gaze, crop, palette, lighting direction, and negative space matched to the SVG composition.
6. Choose the background strategy:
   - Use chroma-key removal for simple opaque or hard-edged subjects.
   - Prefer matched-background generation when hair, fur, smoke, glass, translucency, reflections, or soft shadows do not require later repositioning.
   - Follow the `imagegen` Skill's confirmation gate if true native transparency is required.
7. Save the final transparent subject inside the project, compose it with the SVG layout, and export one PNG/WebP.
8. Inspect the transparent layer and final composition. Iterate with one targeted change at a time.

## Chroma-key subject brief

Use a key color absent from the subject. Default to `#00ff00`; use `#ff00ff` when the subject contains green.

Include these constraints in the generation prompt:

```text
Asset type: transparent cutout subject for a GitHub README hero
Composition/framing: match the reserved hero area; specify body crop, gaze, and facing direction
Color palette: use the repository palette; do not use the selected key color in the subject
Constraints: one isolated subject; generous padding; no text; no letters; no logo; no watermark
Background: perfectly flat solid key color with no gradient, texture, floor, reflection, or shadow
```

Use the installed helper and parameters defined by the `imagegen` Skill. Do not copy or fork its background-removal script into this Skill.

## Composition rules

- Let SVG control typography, exact copy, labels, grids, diagrams, borders, and alignment.
- Let the raster layer provide only the material, character, lighting, or organic detail that benefits from generation.
- Match the generated subject's light direction and edge color to the SVG palette.
- Keep the subject inside a named SVG group or reserved box so it can be replaced without rebuilding the layout.
- Preserve enough contrast around hair, tools, clothing, and other edge details.
- Avoid placing essential proof behind the generated subject.
- Keep commands, links, installation steps, and long explanations in Markdown.

## Validation

For the transparent subject, verify:

- an alpha channel exists;
- all four corners are fully transparent;
- subject coverage is plausible;
- no obvious key-color fringe remains on light or dark backgrounds;
- thin details and intended rim light survive;
- the subject contains no accidental text or watermark.

For the final asset, verify:

- `1200`-pixel GitHub width and a narrow preview;
- readable title and labels;
- clean crop and visual balance;
- no missing local image placeholder;
- acceptable PNG/WebP size;
- meaningful alt text;
- the design still feels native to the repository.

Report the ImageGen mode used, final prompt, transparent asset path, composition source path, published asset path, and any intermediates intentionally retained.
