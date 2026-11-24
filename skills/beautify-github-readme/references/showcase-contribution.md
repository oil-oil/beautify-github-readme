# Optional showcase contribution

Use this workflow only after the user explicitly approves the finished README and opts into sharing a public repository with the `beautify-github-readme` community showcase.

## Eligibility gate

Confirm all of the following before preparing upstream changes:

- The repository is public.
- The user owns, maintains, or is authorized to represent it.
- The finished README (and its hero asset, if present) is already published and visible on the repository's default branch.
- `SHOWCASE.md` in `oil-oil/beautify-github-readme` does not already list the repository.

Do not treat an attribution badge as a requirement. A repository may be proposed with or without the badge.

## Ask once, without pressure

Use neutral wording and make declining easy:

> If you'd like to share this result, I can draft a small PR to add the public repository to `SHOWCASE.md` in `oil-oil/beautify-github-readme`. This is completely optional, and the upstream maintainers will decide whether to merge it.

Do not repeat the offer after a decline. Do not create an issue, discussion, fork, branch, or PR merely because the user expressed satisfaction.

## Target file and asset rules (strict)

- **The ONLY file a community showcase PR may modify is `SHOWCASE.md`.**
- **NEVER modify `README.md`, `README.zh-CN.md`, `README.ja.md`, or any homepage visual assets under `assets/readme/`** (including `section-used-by.svg`, case cards, or theme walls).
- **NEVER commit or copy external images into `assets/` (or any directory) of `oil-oil/beautify-github-readme`.** Always reference the contributor's own live hero image via `https://raw.githubusercontent.com/<owner>/<repo>/<default_branch>/<hero-path>`.
- Homepage `README*.md` files are maintained exclusively by the repository maintainers; any PR that touches them or adds third-party image files will not be accepted as a community showcase entry.

## Prepare the proposal

1. Inspect `SHOWCASE.md` on the latest default branch of `https://github.com/oil-oil/beautify-github-readme`.
2. Check for duplicates in `SHOWCASE.md` and pick the single best-fitting category (`Developer Tools · 开发工具`, `AI & Agent Projects · AI 与 Agent 项目`, or `Creative & Interactive · 创意与交互项目`).
3. Locate the main hero image in the contributor's live README, resolve any relative path to `https://raw.githubusercontent.com/<owner>/<repo>/<default_branch>/<hero-path>`, and verify with `curl -sI` that it returns `HTTP 200` with an image `Content-Type` (`image/svg+xml`, `image/png`, `image/webp`, or `image/gif`).
4. Draft one factual sentence explaining what the finished README demonstrates. Do not invent adoption, testimonials, results, or product capabilities.
5. Add one entry under the matching category in `SHOWCASE.md` using this exact format:
   ```markdown
   ### [Repo Name](https://github.com/owner/repo)

   <p align="center">
     <a href="https://github.com/owner/repo">
       <img src="https://raw.githubusercontent.com/owner/repo/{default_branch}/{hero-path}" width="100%" alt="Repo Name README hero">
     </a>
   </p>

   One factual sentence explaining what the redesigned README demonstrates. / 一句实事求是的中文说明。
   ```
   If the repository's README intentionally has no hero image, omit the `<p align="center">...</p>` image block and keep the heading and one-line description without broken `<img>` tags.
6. Verify that `git diff --name-only` contains **only `SHOWCASE.md`** and no untracked image files were added.
7. Show the exact proposed entry, verified hero URL, and diff to the user for approval before taking any remote action.

## Publish only with explicit approval

After the user approves the exact listing copy and single-file diff, ask for explicit authorization to open the PR. Then:

- Use a normal branch and PR when the authenticated account has upstream access.
- Otherwise use a fork-based PR only if the user authorizes creating or using the fork.
- If neither route is available, provide the prepared patch and PR text without creating external state.
- Report the PR URL and state clearly that upstream maintainers may edit, decline, or merge it.

Never push directly to the upstream default branch. Never imply that a showcase submission is already accepted.
