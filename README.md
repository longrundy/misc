# longrundy.com

Static personal site. No build step, no dependencies. Edit the HTML, push, done.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole page. All content lives here. |
| `styles.css` | All styling. Colors are variables at the top. |
| `CNAME` | Tells GitHub Pages your custom domain. |
| `.nojekyll` | Stops GitHub from running Jekyll on the files. |
| `images/` | Put `lon.jpg` here. |

## Before you publish

1. **Add your photo.** Save a portrait shot as `images/lon.jpg`. Portrait orientation, about 800×1000 pixels or larger. If it's missing, the site shows a sand panel with your initials rather than a broken image.
2. **Add your resume.** Save it as `resume.pdf` in the root folder. If you'd rather not publish a resume yet, delete the "View resume" link from `index.html` (search for `resume.pdf`).
3. **Check the LinkedIn URL.** Near the bottom of `index.html`, in the contact section, confirm `linkedin.com/in/longrundy` is right. Delete that link if you don't want it.
4. **Confirm the current dates.** The World Golf Village entry says 2018 to present, and the hero says thirty-five years. Update both if needed.

## Deploying to GitHub Pages

1. Create a repository. Name it anything — `longrundy.com` works.
2. Upload every file in this folder, keeping the `images/` folder as a folder. Drag and drop works in the GitHub web UI.
3. Go to **Settings → Pages**. Under "Build and deployment," set Source to **Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. On the same Pages screen, the Custom domain box should already read `longrundy.com` because of the `CNAME` file. If not, type it in and save.
5. Wait for the DNS check to pass, then tick **Enforce HTTPS**.

## DNS at your registrar

For the apex domain `longrundy.com`, create four A records pointing at GitHub:

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

And one CNAME record so the www version works too:

```
Host: www    Value: YOUR-GITHUB-USERNAME.github.io
```

DNS changes usually take under an hour but can take up to 24. GitHub's Pages settings screen will tell you when it sees the records.

## Editing later

- **Text**: open `index.html` and edit between the tags. The structure is commented by section.
- **Colors**: the top of `styles.css` has five variables — `--ink`, `--paper`, `--sand`, `--sea`, and their variants. Change those and the whole site follows.
- **Adding a role**: copy an existing `<li class="role">` block and edit it. The `role-current` class is what makes the teal dot on the top entry, so only one entry should have it.
- **Accomplishment lists**: those are `<details>` blocks, which collapse by default. Add `open` to the tag if you want one expanded on page load.
