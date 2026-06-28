# Updating your website

This is your plain-language guide to keeping the site current. You do **not**
need to write code or run anything on your computer — every change can be made
by editing a file on GitHub.com and clicking **Commit changes**. About a minute
after you save, the site rebuilds and republishes itself automatically.

Your site lives at **https://mingpuxiao.github.io/mingpu-site/**

---

## The 30-second mental model

- **Words** (your bio, name, email, advisors) live in two files:
  `hugo.yaml` and `content/_index.md`.
- **Lists** (papers, teaching, photos) live in the `data/` folder as simple
  `.yaml` files. Each entry starts with a `-`.
- **Files** (your CV, paper PDFs, photos) live in the `static/` folder.
- **Look and feel** (colors) lives at the top of `assets/css/style.css`.

To edit any file on GitHub: open it, click the **pencil icon** (top right),
make your change, then click the green **Commit changes** button.

---

## Common tasks

### Change your bio
Edit `content/_index.md`. The text below the `---` line is your bio. Leave a
blank line between paragraphs.

### Change your name, email, university, advisors, or research interests
Edit `hugo.yaml`. These are near the top under `params:`. Keep the quotation
marks.

### Add or update a paper
Edit `data/papers.yaml`. Copy an existing block and change the values. The page
sorts papers automatically into three groups based on the `status:` line:

- `status: "job market paper"` + `job_market_paper: true` → the highlighted card
- `status: "working paper"` (or `"under review"`, `"revise and resubmit"`) → **Working Papers**
- `status: "published"` (or `"forthcoming"`, `"accepted"`) → **Publications**

A minimal entry:

```yaml
- title: "My New Paper Title"
  coauthors: ["Jane Coauthor"]    # leave out if solo-authored
  status: "under review"
  year: 2026
  pdf: "files/my-paper.pdf"       # optional; see "Add a PDF" below
  link: ""                        # or an external URL instead of a PDF
```

### Add a PDF (CV or a paper)
1. Put the PDF in the `static/files/` folder (on GitHub: open the folder →
   **Add file → Upload files**).
2. **For a paper:** point to it from `data/papers.yaml` with
   `pdf: "files/your-file.pdf"`.
3. **For your CV:** name the file `cv.pdf`, then open `hugo.yaml` and add a CV
   link to the menu (the file already has the lines you need, commented out —
   just remove the `#` marks):

   ```yaml
       - name: "CV"
         url: "/files/cv.pdf"
         weight: 25
   ```

### Add or change a course
Edit `data/teaching.yaml`. Copy an existing block.

### Add a photo to "Beyond Research"
1. Resize the photo so its longest side is about 1200 pixels (keeps the page
   fast), then upload it to `static/images/hikes/`.
2. Add an entry to `data/photos.yaml` with a short description for `alt:`.

### Change the colors
Edit the very top of `assets/css/style.css` — the `--color-accent` value
controls links and highlights. Use any hex color.

---

## Tips

- **Keep the quotation marks and the indentation** in the `.yaml` files. YAML
  cares about spacing (two spaces, never tabs).
- If something looks broken after an edit, open the **Actions** tab on GitHub.
  A red ✗ means the build failed — click it to see the message, or undo your
  last commit (each file's **History** lets you revert).
- Changes appear at the live URL about a minute after you commit.
