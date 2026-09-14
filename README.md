# Jason Allen Web Solutions — website

Built with [Astro](https://astro.build). Deploys automatically to GitHub
Pages at **jasonallen.us** via GitHub Actions on every push to `main`.

## 1. Open it in VS Code and run it locally

Unzip the project, then in VS Code: **File > Open Folder** and select the
`jasonallen-site` folder. Open a terminal (Terminal > New Terminal) and run:

```bash
npm install
npm run dev
```

Open the URL it prints (usually `http://localhost:4321`) to preview.
Edit files in `src/` — the browser reloads automatically.

## 2. Push it to GitHub (using what you set up in VS Code)

In the VS Code terminal:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
git push -u origin main
```

Or use the Source Control panel (Ctrl+Shift+G) → "Initialize Repository" →
"Publish to GitHub" instead of the commands above.

## 3. Turn on GitHub Pages

In your GitHub repo: **Settings → Pages → Build and deployment → Source**,
select **GitHub Actions**. The included workflow
(`.github/workflows/deploy.yml`) builds and deploys on every push — check
the **Actions** tab for progress.

## 4. Point jasonallen.us at GitHub Pages

At your domain registrar / DNS provider, add:

- Four **A** records for the apex domain (`jasonallen.us`) pointing to:
  `185.199.108.153`, `185.199.109.153`, `185.199.110.153`,
  `185.199.111.153`
- A **CNAME** record for `www` pointing to `YOUR-USERNAME.github.io`

Then in the repo: **Settings → Pages → Custom domain**, enter
`jasonallen.us` and save (a `public/CNAME` file with that domain is
already included, so GitHub Pages recognizes it automatically). Once DNS
propagates, check **Enforce HTTPS**.

## 5. What's placeholder right now

- **Client logos** (CAM, Power Core Peptides, Axis, Summit, Brighter
  Futures) are simple text wordmarks, not real logo files — swap in real
  logo images when you have them.
- **Project screenshots** in the Featured Projects section are abstract
  CSS mockups standing in for real site screenshots.
- **Social links** in the footer point to `#` — add your real profile
  URLs.
- **Blog** — there's a nav link and footer link to Blog, but no blog
  pages yet. Say the word and I'll set up an Astro content collection so
  you can write posts in Markdown.
- **Phone number** in the footer is transcribed from your mockup —
  double check it's the one you want public.

## Project structure

```
src/
  components/   Header, Hero, TrustedBy, Services, Projects, Process,
                Technologies, Testimonials, Pricing, CtaBanner, Footer
  layouts/      Layout.astro (page shell, fonts, meta tags)
  pages/        index.astro (assembles the homepage)
  styles/       global.css (color/type tokens, resets)
public/
  CNAME         custom domain for GitHub Pages
  favicon.svg
.github/workflows/deploy.yml   builds and deploys on every push to main
```
