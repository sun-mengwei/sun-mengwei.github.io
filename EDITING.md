# Editing your academic website

Your website uses two files: `index.html` holds the words and links, and `styles.css` controls the appearance. You can edit and preview everything locally before committing anything to GitHub. The public website is [sun-mengwei.github.io](https://sun-mengwei.github.io/).

**1. Open the files in a text editor.**

The website folder is:

```text
/Users/mengwei/Documents/ChatGPT/New project/personal-website
```

In Finder, press **Command–Shift–G**, paste that path, and press Return. Open `index.html` with a code editor or a plain-text editor. Avoid Word or rich-text editing, which can change the file format. Keep the filename `index.html`.

HTML tags describe the structure. For most changes, replace only the words between the opening and closing tags:

```html
<p class="profile-name">Mengwei Sun</p>
```

Keep `<p class="profile-name">` and `</p>` when editing the displayed name. Remove the square brackets when replacing a placeholder. Text inside `<!-- ... -->` is a comment for you; it does not appear on the page.

**2. Fill in your name and sidebar.**

Your name is already set to `Mengwei Sun`, including the browser-tab title and description near the top. Find the `PROFILE` comment to update your position, field, and institution. `<br>` starts a new line.

Your email, GitHub, and LinkedIn entries are clickable links inside `<ul class="contact-list">`. Each list item contains an `<a>` link, an inline `<svg>` icon, and a visible text label.

To change a destination, edit only its `href` value and leave the SVG markup intact:

```html
href="mailto:msun351@gatech.edu"
href="https://github.com/sun-mengwei"
href="https://www.linkedin.com/in/mengwei-s-6983091b0/"
```

The text inside `<span>GitHub</span>` or `<span>LinkedIn</span>` is the visible label. Keep the `aria-label` descriptive so the links are easy to identify with a screen reader.

To omit a contact item, remove its entire `<li>...</li>` entry. The icon sizes and spacing are controlled by `.contact-icon` and `.contact-item` in `styles.css`.

**3. Write your introduction.**

Find the `ABOUT` comment. Replace the two paragraphs below the “About me” heading. Each `<p>...</p>` is one paragraph:

```html
<p>I am a [position] at [institution]. My research focuses on [topics].</p>
<p>[A short note about your academic background and current work.]</p>
```

One or two short paragraphs will preserve the concise layout. You can delete the second paragraph if it is unnecessary. Leave the section's `id="about"` unchanged so the navigation continues to work.

**4. Restore Projects later, when ready.**

The Projects section is currently removed. To restore it, insert the following inside `<main>`, between the About me and Teaching sections. Replace the description before showing it on the website:

```html
<section id="projects" aria-labelledby="projects-title">
  <h2 id="projects-title">Projects</h2>
  <article>
    <h3>Game dynamics</h3>
    <p>[The question you study, your approach, and your current progress.]</p>
  </article>
</section>
```

Then restore the navigation link inside `<nav>`, between About and Teaching:

```html
<a href="#projects">Projects</a>
```

For another project, copy the complete `<article>...</article>` block inside the Projects section, before its closing `</section>`. Do not duplicate the section itself or its `id`. Add a repository link only when you have a real destination.

You can also add a report PDF to the folder and link it with `<a href="./report.pdf">Project report</a>`.

**5. Add your teaching experience.**

Find the `TEACHING` comment. Replace the existing article with your course details:

```html
<article>
  <div class="entry-heading">
    <h3>[Course code and title]</h3>
    <span class="term">[Term, year]</span>
  </div>
  <p class="entry-meta">[Your role] · [Institution]</p>
  <p>[A short description of your responsibilities.]</p>
</article>
```

Copy the whole article for each additional course, placing it inside the same Teaching section. List the most recent experience first. Use your actual role, such as instructor, teaching assistant, or tutor.

**6. Save and preview.**

Press **Command–S** in your editor, then refresh the browser. This static site does not refresh automatically when you save.

The simplest preview is to open `index.html` directly in your browser. Keep `styles.css` beside it so the styling loads.

Alternatively, use the existing local preview at `http://127.0.0.1:4173/`. If it is no longer running, open Terminal and run:

```sh
cd "/Users/mengwei/Documents/ChatGPT/New project/personal-website"
python3 -m http.server 4173 --bind 127.0.0.1
```

Leave that Terminal session running while reviewing the site. Press **Control–C** in that session to stop the server. If the command reports “Address already in use,” try the existing preview first; a server may already be running.

After editing, click the navigation and your real links, and narrow the browser window to check the phone layout. If a change is missing, make sure you saved the file and are previewing the correct folder; a hard refresh can help with cached styling.

**7. Adjust the design only if needed.**

Open `styles.css`. The current blue is defined near the top:

```css
--accent: #2349cf;
```

You can keep the existing design and edit only the HTML. If you do change styling, these are the main controls:

| What to change | Where in `styles.css` |
| --- | --- |
| Link color | `--accent` |
| Main text color | `--ink` |
| Background | `--page` |
| Space between sections | `section + section` → `margin-top` |
| Section heading size | `h1, h2` → `font-size` |

The `@media` rules near the bottom adapt the layout to smaller screens and printing. Keep them unless you intend to change those layouts too. If you change the blue, update the theme-color and favicon in the HTML head as well for consistency.

**8. Publish your changes.**

Saving a file changes only your local copy. After reviewing it, run these commands in the website folder to publish your edits:

```sh
git status
git add index.html styles.css
git commit -m "Update academic website"
git push origin main
```

If you added a new file, include its name in the `git add` command too. GitHub Pages automatically publishes the `main` branch; the update can take a few minutes. Check the repository's **Actions** tab if a deployment fails.

For a small text correction, you can also open `index.html` in the [GitHub repository](https://github.com/sun-mengwei/sun-mengwei.github.io), click the pencil icon, edit the text, and commit the change. This updates the public site. Run `git pull --ff-only` locally before your next local edit to bring that change back to your computer.
