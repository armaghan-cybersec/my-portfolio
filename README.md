# M Armaghan Arshad — Cyber Security Portfolio

A lightweight, responsive, recruiter-focused portfolio for **M Armaghan Arshad**, a BS Cyber Security student at the University of Haripur. It is intentionally built with semantic HTML, modern CSS, and vanilla JavaScript so it can be understood, edited, and hosted free on GitHub Pages.

## Technologies

- Semantic HTML5
- CSS3 (responsive layout, accessible focus states, reduced-motion support)
- Vanilla JavaScript (mobile menu and current copyright year)
- GitHub Pages / GitHub Actions
- No backend, database, analytics, paid API, or build system

## File structure

```text
portfolio/
├── index.html                 # Main one-page portfolio
├── 404.html                   # GitHub Pages fallback page
├── README.md                  # This guide
├── .nojekyll                  # Prevents Jekyll processing
├── css/style.css              # Design system and responsive styles
├── js/script.js               # Mobile menu and progressive enhancement
├── assets/favicon.svg         # Small initials-based favicon
├── projects/README.md         # Case-study evidence guidance
├── documents/README.md        # Future CV/document guidance
└── .github/workflows/pages.yml# Optional official Pages deployment workflow
```

## Run locally

From this directory, start any simple static server:

```bash
python3 -m http.server 8000
```

Open `http://localhost:8000`. Because this is a static site, no `npm install` or build step is required. You can also open `index.html` directly, but a local server better matches GitHub Pages behavior.

## Update personal content

Most profile content is intentionally visible in `index.html`, so a beginner can update it without a framework:

1. Edit the name, biography, headline, education, location, and opportunity language in the hero/about sections.
2. Update the four skill cards only when the knowledge description remains accurate.
3. Change `Planned` to `In progress` or `Completed` only when the corresponding project work genuinely supports that status. Add repository/report links only when real links exist.
4. Update course tags only when the status is verifiable. Do not add certificate IDs, dates, or URLs without evidence.
5. Replace the three profile URLs and email only if your public contact details change.
6. The current year in the footer is inserted by `js/script.js`; it should not need manual updates.

## Add a real CV later

No fabricated résumé or broken download action is included. When a real PDF is ready:

1. Put it at `documents/M-Armaghan-Arshad-CV.pdf`.
2. Replace the `cv-placeholder` element in `index.html` with a normal link:

```html
<a href="documents/M-Armaghan-Arshad-CV.pdf" target="_blank" rel="noopener noreferrer">
  <span>CV / résumé</span><span aria-hidden="true">↗</span>
</a>
```

3. Test the relative link locally before publishing. Keep the PDF free of private identity documents, passwords, tokens, and unnecessary sensitive information.

## Add project evidence

Use `projects/README.md` as the case-study checklist. Store only appropriate public material. A future project card should include a real status, problem, objective, scope/environment, tools, method, implementation notes, evidence, findings, recommendations, limitations, lessons learned, and real repository/report links. Never invent event totals, screenshots, attack results, or incident outcomes.

## Create the GitHub repository

1. Create a new GitHub repository. A user site can use the repository name `<username>.github.io`; a project site can use any repository name.
2. Keep the repository public if you want recruiters to inspect the source. Review every file before publishing.
3. From this folder:

```bash
git init
git add .
git commit -m "Build cybersecurity portfolio"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
git push -u origin main
```

Replace the remote URL with your actual repository URL.

## Publish with GitHub Pages

This repository includes `.github/workflows/pages.yml`, which uses GitHub's current Pages actions. On GitHub:

1. Open **Settings → Pages**.
2. Under **Build and deployment**, choose **GitHub Actions**.
3. Push to `main`; the workflow uploads the repository as a Pages artifact and deploys it.
4. In **Actions**, inspect the workflow run. In **Settings → Pages**, GitHub shows the deployed URL.

Reference: [GitHub Pages documentation](https://docs.github.com/en/pages/getting-started-with-github-pages).

If you prefer branch-based publishing, choose **Deploy from a branch**, select `main` and the `/ (root)` folder, then save. Do not use both methods at once.

### URL and metadata

The site intentionally has no invented canonical URL. After you know the real public URL, add a canonical `<link>` and any final `og:url` value to `index.html`. Relative paths are used so assets work at both a user-site root and a project-site subpath.

## Updating after deployment

Edit locally, run the checks below, then:

```bash
git add .
git commit -m "Update portfolio content"
git push
```

GitHub Actions redeploys after a successful push to `main`.

## Troubleshooting

- **404 on assets:** use relative paths such as `css/style.css`, not `/css/style.css`. Confirm the repository Pages source and case-sensitive file names.
- **404 on project-site homepage:** verify the Pages URL includes the repository name, or use a user-site repository named `<username>.github.io`.
- **Workflow fails:** open the failed Actions run, check the permissions and Pages settings, and confirm the repository is not blocked by an organization policy.
- **Menu does not open:** confirm `js/script.js` exists, the script path is relative, and the browser console has no errors.
- **Old content appears:** hard-refresh, check the latest commit, and inspect the Pages deployment run.

## Pre-publication checklist

- [ ] Profile name, education, location, email, and links are correct.
- [ ] Skills still describe genuine knowledge, not desired future skills.
- [ ] Planned projects are not presented as completed.
- [ ] Course statuses are verified and accurate.
- [ ] No passwords, API keys, tokens, private credentials, or sensitive documents are present.
- [ ] A real CV exists before enabling a CV link.
- [ ] Links work at the final GitHub Pages path.
- [ ] Mobile menu works with keyboard and Escape.
- [ ] The repository has been reviewed because public repository content may be visible to anyone.
- [ ] The deployed page has been checked at mobile, tablet, and desktop widths.
