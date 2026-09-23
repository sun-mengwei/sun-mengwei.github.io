# Mengwei Sun — Academic Website

A simple academic website for GitHub Pages, written in plain HTML and CSS. No dependencies or build step.

Website: [sun-mengwei.github.io](https://sun-mengwei.github.io/).

For step-by-step instructions and copyable examples, see [Editing your academic website](EDITING.md).

## Page structure

A compact academic layout, retaining the original blue accent (`#2349cf`).

- **Left sidebar** — a small portrait, name, position, affiliation, email, GitHub, and LinkedIn, with small blue icons.
- **About me** — a concise personal introduction, including research interests.
- **Research** — learning-based methods for dynamical systems, with the Deep Tangent Bundle description followed by the project figure and GitHub link.
- **Teaching** — MATH 2551 (TA), MATH 4640 (LA), and MATH 3670 (LA) at Georgia Tech, with titles linked to the official course pages.

On small screens, the sidebar sits above the main content. Research projects appear in the Research section; see the editing guide to add more. There is no publications section. Mengwei Sun’s name, biography, academic affiliation, email, and teaching courses have been supplied. The email, GitHub, and LinkedIn links are active. Teaching terms and responsibilities have not yet been provided and are omitted.

## Preview

Open `index.html` directly in a browser, or serve this folder:

```sh
python3 -m http.server 4173 --bind 127.0.0.1
```

Then visit `http://127.0.0.1:4173`.

## Customize

- Edit the biography, sidebar, research projects, and teaching entries in `index.html`. Comments mark the relevant blocks.
- Update the page title and description when changing the profile.
- Update social profile destinations in the sidebar anchors if your URLs change.
- The email already uses a clickable `mailto:` link.
- Change the colors, type, and layout in `styles.css`; the main colors are defined at the top.
- There are no external fonts, scripts, trackers, images, or network dependencies.

The project figure, `images/game-dynamics-comparison.png`, is the two-panel image supplied for this website: periodic full-basis refitting and the RK4 reference at ω/π = 4. The panels come from [the project's oscillatory particle-cloud comparison](https://github.com/sun-mengwei/deep-tangent-bundle-method-for-game-dynamics/blob/main/docs/images/oscillatory-clouds.png), originally Report Figure 7. They show historical report results, not a new execution of the notebooks. Clicking the figure opens the full-resolution image.

## GitHub Pages

The repository is [sun-mengwei/sun-mengwei.github.io](https://github.com/sun-mengwei/sun-mengwei.github.io). GitHub Pages serves the root of the `main` branch. The included `.nojekyll` file allows the files to be served directly. Pushing a new commit to `main` publishes an update automatically.

The same files work for a project site because asset links are relative.

Reference: [Creating a GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site).

## Brief references

- [Academic Pages layout reference](https://github.com/academicpages/academicpages.github.io/blob/master/images/themes/homepage-light.png) — compact left sidebar and main academic content column.

- [GitHub personal-website topic](https://github.com/topics/personal-website) — examples of personal portfolio sites.
- [Career portfolio](https://en.wikipedia.org/wiki/Career_portfolio) — context for showing a biography and examples of work.

The template uses original markup and styling; no third-party template was copied.

The inline email, GitHub, and LinkedIn icons are from [Bootstrap Icons](https://icons.getbootstrap.com/) under the MIT license. See `THIRD-PARTY-NOTICES.txt`.
