# parinitanema.github.io

Personal academic site for Parinita Nema — PhD candidate, Department of Data Science
and Engineering, IISER Bhopal.

Plain HTML, CSS and JavaScript. No build step, no framework, nothing to install.

---

## Files

```
index.html                    the whole site (HTML + CSS + JS in one file)
favicon.svg                   browser tab icon
.nojekyll                     tells GitHub Pages to serve the files as-is
assets/
  Parinita_Nema_CV.pdf        linked from the hero and the contact section
  gofor-framework.png         Figure 1 from the BMVC paper
  portrait.jpg                NOT INCLUDED — add your own photo here (see below)
README.md                     this file
```

---

## Putting it online

Your repo `Parinitanema/Parinitanema.github.io` is a GitHub **user site**, so
whatever sits on the default branch is published at <https://parinitanema.github.io/>.

### Option A — upload through the browser (no git needed)

1. Open <https://github.com/Parinitanema/Parinitanema.github.io>
2. Click **Add file → Upload files**
3. Drag in `index.html`, `favicon.svg`, `.nojekyll`, `README.md`, **and the whole
   `assets` folder** (drag the folder itself so the paths stay intact)
4. Write a commit message, click **Commit changes**
5. Go to **Settings → Pages** and check that Source is *Deploy from a branch*,
   branch `main`, folder `/ (root)`
6. Wait 1–2 minutes, then open <https://parinitanema.github.io/>

If the old site is still showing, do a hard refresh (Ctrl+Shift+R / Cmd+Shift+R).

### Option B — git from your machine

```bash
git clone https://github.com/Parinitanema/Parinitanema.github.io.git
cd Parinitanema.github.io
# copy the contents of this folder in here, then:
git add .
git commit -m "New personal site"
git push
```

---

## About the photo

There is **no photo in this package**. The contact section shows a "PN" monogram
until you add one — drop a file at `assets/portrait.jpg` and it swaps itself in
automatically. No code change needed.

What works well:

- **Square crop, about 800×800 px**, head and shoulders, you looking at the camera
- Plain, uncluttered background — a wall, a corridor, outdoors with the background
  thrown out of focus. Not a busy lab bench.
- Even daylight. A window on your left or right beats overhead fluorescent light.
- Save as JPEG, quality ~80, **under 300 KB** so the page stays fast
- A phone portrait-mode photo taken by a labmate is completely fine. This does not
  need a studio.

Please don't use the cartoon avatar that is sitting in your Overleaf CV project —
it reads as a placeholder on an academic page.

### Other images worth adding

The strongest images on a research site are **your own figures**. `assets/gofor-framework.png`
is Figure 1 from your BMVC paper, already cropped out of the PDF. You can add the
same kind of teaser for the other papers:

- WACV 2025 — your base-representation / feature-augmentation figure
- Interspeech 2024 — the contrastive representation figure
- A result plot from GOFOR (the Split ImageNet-R comparison would land well)

To crop a figure out of a paper PDF: open the PDF, screenshot the figure at maximum
zoom, save as PNG into `assets/`, then copy the `<figure class="teaser">` block from
the BMVC entry in `index.html` and point it at your new file.

Avoid stock photos of robots, glowing brains or blue circuit boards. They make a
research page look generic, and reviewers notice.

---

## Things to edit before you share the link

Search `index.html` for these:

1. **`PASTE_SCHOLAR_URL`** — there is a commented-out Google Scholar link in the
   contact section. Paste your profile URL and delete the `<!--` and `-->` around it.
2. **`PASTE_PDF_URL` / `PASTE_CODE_URL`** — a commented-out links row under the BMVC
   paper. Uncomment once the paper and code are online, and copy the same pattern to
   the other papers.
3. **"Prize, 3-minute research presentation"** — replace with the exact award name
   from the Energy and AI symposium.
4. **"Last updated August 2026"** in the footer.

## Keeping it current

- **New paper:** copy an existing `<li class="pub">` block, change the text, and give
  it a new colour. To add a fifth cluster to the hero plot, add one entry to the
  `CLASSES` array in the script at the bottom and a matching `--c5`-style colour
  variable at the top.
- **New CV:** replace `assets/Parinita_Nema_CV.pdf`, keeping the same filename so the
  links keep working.

## How the hero plot works

The scatter plot in the hero is a feature space where each cluster is one of your
papers, arriving in publication order — the clusters that arrived earlier stay
exactly where they are as new ones appear. The stars are class prototypes.

Hovering a legend entry highlights that cluster; clicking it jumps to the paper.
Hovering a paper in the publication list highlights its cluster. Everything animates
only for visitors who have not asked for reduced motion.
