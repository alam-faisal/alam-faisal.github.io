# TODO

## Immediate — required to go live

- [ ] **Switch GitHub Pages source to GitHub Actions**
  Go to: GitHub repo → Settings → Pages → Source → select **"GitHub Actions"** (not "Deploy from branch").
  This is the only manual step. Without it the old Jekyll pipeline runs and the site won't update.

- [ ] Commit and push the new code to `master`
  ```
  git add -A
  git commit -m "Migrate to Astro"
  git push
  ```
  After pushing, the Actions workflow at `.github/workflows/deploy.yml` will build and deploy automatically (~1 min).

## Content — fill in soon

- [ ] Verify profile2.jpg looks good at 108px circular crop (check the live site after deploy)
- [ ] Check the Hamming code blog post renders correctly on mobile (math overflow, code block scroll)
- [ ] Update the LinkedIn URL if needed — current: `/in/faisal-alam-a19981274` (check this is still correct)

## When you write new blog posts (Obsidian workflow)

1. Write in Obsidian using `$...$` / `$$...$$` for math and `![alt](/images/file.png)` for figures
2. Add YAML frontmatter at the top:
   ```yaml
   ---
   title: "The Steane Code"
   date: 2025-09-15
   description: "One sentence for the blog index."
   ---
   ```
3. Put any images in `public/images/` in the repo
4. Drop the `.md` file into `src/content/blog/`
5. `git push` → site updates automatically

Note: Obsidian's `[[wikilink]]` syntax won't render — use standard `[text](url)` links instead.

## Future additions (not urgent)

- [ ] Favicon — add a small favicon to `public/`. Currently serving none.
- [ ] Open Graph meta tags — for nice previews when links are shared on Slack/Twitter. Add `og:title`, `og:description`, `og:image` to `Base.astro`.
- [ ] Syntax highlighting theme — if the current warm code block style doesn't feel right, try changing `shikiConfig.theme` in `astro.config.mjs`. Options: `'one-light'`, `'catppuccin-latte'`, `'github-light'` (current).
- [ ] Publications page — once you have ≥8 papers, add `/src/pages/publications.astro` and link it in the nav. For now the 3 on the homepage is the right call.
- [ ] Google Analytics / Plausible — add a snippet to `Base.astro` if you ever want traffic data.
- [ ] Upgrade Astro — pinned to `^4.16.0`. When Astro 5 content collection API is needed, the main change is `import { render } from 'astro:content'` + `const { Content } = await render(post)` instead of `post.render()`.
