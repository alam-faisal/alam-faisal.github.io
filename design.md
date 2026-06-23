# Website Design — Finalized

## Decisions

| Decision | Choice |
|---|---|
| Pages | 2: Home (`/`) + Blog (`/blog`) |
| Tech stack | Astro (static) + GitHub Actions deploy |
| Palette | Warm Paper |
| Typography | EB Garamond headings + Source Serif 4 body + JetBrains Mono code |
| Math | KaTeX via rehype-katex (server-side, no JS needed) |
| Code highlighting | Shiki (github-light theme, warm bg override) |
| Profile photo | `images/profile2.jpg` → `public/images/profile2.jpg` |
| Blog URL format | `/blog/slug` (no year prefix) |
| Email | faisal@phasecraft.io |

## Palette — Warm Paper

| Role | Hex |
|---|---|
| Background | `#F9F7F4` |
| Text | `#1C1917` |
| Accent (amber) | `#B45309` |
| Link / secondary | `#3D5A80` |
| Muted text | `#78716C` |
| Code background | `#F0EDE8` |
| Border | `#E7E2DB` |

## Typography

- **Headings:** EB Garamond (400, 600 weights)
- **Body:** Source Serif 4 (400, 600 weights, optical-size range 8–60)
- **Code/mono:** JetBrains Mono (400 weight)
- Base size: 17px / line-height 1.68
- Column max-width: 680px content, 780px container

## Page structure

### Home (`/`)
1. Nav — "Faisal Alam" left · "Blog" + "CV" right (sticky)
2. Hero — circular photo (profile2.jpg, 108px) + name + subtitle + bio text + research list + links
3. Selected publications — 3 papers (see below)
4. Footer — email left · Scholar / GitHub / LinkedIn right

### Blog index (`/blog`)
- Post list sorted by date descending: title + date + description

### Blog post (`/blog/[slug]`)
- Post header: title + date
- Article content: full markdown with KaTeX math and Shiki code

## Featured publications (in order shown)

1. **Onset of Ergodicity Across Scales on a Digital Quantum Processor** — arXiv:2603.12236 · March 2026 · preprint
2. **Transmon qutrit-based simulation of spin-1 AKLT systems** — arXiv:2412.19786 · December 2024 · preprint
3. **Learning dynamic quantum circuits for efficient state preparation** — arXiv:2410.09030 · October 2024 · preprint

## Obsidian → blog workflow

Write in Obsidian using:
- Standard markdown
- `$...$` for inline math, `$$...$$` for display math (same as KaTeX default)
- `![alt](/images/filename.png)` for images (files go in `public/images/`)
- YAML frontmatter:
  ```yaml
  ---
  title: "Post Title"
  date: 2025-05-22
  description: "One-line description for the post index."
  ---
  ```
Drop the `.md` file into `src/content/blog/`, push. Done.

## One manual step required

After pushing the new code, go to the GitHub repo **Settings → Pages** and change **Source** from "Deploy from a branch" to **"GitHub Actions"**. This only needs to be done once.
