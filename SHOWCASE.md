# Community Showcase · 社区真实案例

> **Submission Rule / 投稿规则**
>
> All community showcase submissions are collected **exclusively in this `SHOWCASE.md` file**.
> Please **do not modify** `README.md`, `README.zh-CN.md`, `README.ja.md`, or any homepage visual assets under `assets/readme/`, and **never commit or copy external image files into this repository** — reference your repository's own live hero image via `raw.githubusercontent.com`.
>
> 所有社区真实案例统一收录于本文件 **`SHOWCASE.md`**。提 PR 时请**仅修改 `SHOWCASE.md`**，不要改动首页 `README.md`、`README.zh-CN.md`、`README.ja.md`，也**不要向本仓库提交任何外部图片文件**（请通过 `raw.githubusercontent.com` 直接引用你仓库自己已发布的首图）。

[← Back to English README](./README.md) · [返回简体中文 README](./README.zh-CN.md) · [日本語 README へ戻る](./README.ja.md)

---

## Developer Tools · 开发工具

### [torqueDASH-Next](https://github.com/moesix/torque-dash-next)

<p align="center">
  <a href="https://github.com/moesix/torque-dash-next">
    <img src="https://raw.githubusercontent.com/moesix/torque-dash-next/master/imgs/hero.svg" width="100%" alt="torqueDASH-Next README hero">
  </a>
</p>

Uses a project-native SVG hero with OBD-II PID data and a real dashboard screenshot to explain a self-hosted vehicle telemetry dashboard. / 用项目原生 SVG 标题和真实仪表盘截图，展示一个自托管车辆遥测仪表盘。

---

## AI & Agent Projects · AI 与 Agent 项目

<!-- Submit AI / Agent / Skill / LLM workflow repositories here using the visual entry format below -->

---

## Creative & Interactive · 创意与交互项目

### [summertown](https://github.com/SummerPapaya/summertown)

<p align="center">
  <a href="https://github.com/SummerPapaya/summertown">
    <img src="https://raw.githubusercontent.com/SummerPapaya/summertown/main/assets/readme/hero.svg" width="100%" alt="summertown README hero">
  </a>
</p>

Uses a seaside-map hero and landmark showcase to introduce an interactive town map. / 用海滨地图主视觉和地标展示，介绍一个可交互的小镇地图。

---

## How to Submit · 如何投稿

1. Make sure your repository is public, you own or maintain it, and the finished README is already live on the default branch.
2. Resolve your repository's published README hero image to its external raw GitHub URL:
   `https://raw.githubusercontent.com/<owner>/<repo>/<default_branch>/<hero-path>`
   and verify it returns `HTTP 200` (image `Content-Type`) before opening your PR.
3. Add **one entry** under the matching category above in **`SHOWCASE.md` only**:
   ```markdown
   ### [Repo Name](https://github.com/owner/repo)

   <p align="center">
     <a href="https://github.com/owner/repo">
       <img src="https://raw.githubusercontent.com/owner/repo/{default_branch}/{hero-path}" width="100%" alt="Repo Name README hero">
     </a>
   </p>

   One factual sentence explaining what the redesigned README demonstrates. / 一句实事求是的中文说明。
   ```
   *(If your README intentionally has no hero image, omit the `<p align="center">...</p>` image block and keep the heading plus the one-line description.)*
4. Open a PR modifying **`SHOWCASE.md` only**. **Never** modify `README.md`, `README.zh-CN.md`, `README.ja.md`, or commit/copy any images into `assets/` of `oil-oil/beautify-github-readme`.

Using a `README MADE WITH` footer signature is optional and never required. All submissions remain subject to maintainer review. See [showcase-contribution.md](./skills/beautify-github-readme/references/showcase-contribution.md) for the full Skill workflow.
