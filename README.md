# parinitanema.github.io

Personal academic website for **Parinita Nema** — Ph.D. candidate, Department of Data
Science and Engineering, IISER Bhopal.

Plain HTML, CSS and JavaScript. No build step, no framework, nothing to install.

---

## Files

```
index.html                  the whole site (HTML + CSS + JS in one file)
favicon.svg                 browser tab icon
.nojekyll                   tells GitHub Pages to serve files as-is
assets/
  portrait.jpg              your photo, already cropped square (900x900)
  Parinita_Nema_CV.pdf      linked from the hero and contact card
  gofor-framework.png       Figure 1 from your BMVC paper
  campus/                   EMPTY - put IISER Bhopal photos here (see below)
README.md                   this file
```

---

## Putting it online

Your repo `Parinitanema/Parinitanema.github.io` is a GitHub **user site**, so whatever
sits on the default branch is published at <https://parinitanema.github.io/>.

### Option A - upload through the browser (no git needed)

1. Open <https://github.com/Parinitanema/Parinitanema.github.io>
2. **Add file -> Upload files**
3. Drag in `index.html`, `favicon.svg`, `.nojekyll`, `README.md`, **and the whole
   `assets` folder** (drag the folder itself so the paths stay intact)
4. Commit the changes
5. **Settings -> Pages** - Source: *Deploy from a branch*, branch `main`, folder `/ (root)`
6. Wait 1-2 minutes, then open <https://parinitanema.github.io/>

If the old site still shows, hard refresh: Ctrl+Shift+R (Cmd+Shift+R on Mac).

### Option B - git

```bash
git clone https://github.com/Parinitanema/Parinitanema.github.io.git
cd Parinitanema.github.io
# copy the contents of this folder in here, then:
git add .
git commit -m "New personal website"
git push
```

---

## Adding the IISER Bhopal photos

There is a **"Where I work"** section already built into the page. It is **hidden right
now** because `assets/campus/` is empty - the page checks each photo and only shows the
section once real images are there. Nothing looks broken in the meantime.

To switch it on, put your photos here with exactly these names:

| File | Suggested subject |
|---|---|
| `assets/campus/campus-1.jpg` | IISER Bhopal campus - main gate, academic block, or a wide shot of the Bhauri campus |
| `assets/campus/campus-2.jpg` | Your department building, or the DSE floor / corridor sign |
| `assets/campus/campus-3.jpg` | Your lab, your desk with work on screen, or your research group |

The section handles 1, 2 or 3 photos - it adjusts the layout automatically. If you only
have one good photo, add just `campus-1.jpg` and delete the other two `<figure>` blocks.

**Photo tips:**

- **Landscape orientation**, roughly 1600x1000 px, saved as JPEG under 400 KB each
- Shoot on a clear day, ideally morning or late afternoon - harsh noon light flattens buildings
- Straight-on architecture shots read as more formal than tilted angles
- A photo of you presenting at a conference or standing at your poster is excellent
  material - if you have one from WACV 2025, it belongs here

**Use photos you took yourself, or official IISER Bhopal photos you have permission to
use.** Don't pull images off Google Images - they are usually copyrighted, and a takedown
notice on your own academic site is a headache you don't need. The institute's
communications office can usually supply high-resolution campus photos on request.

Please avoid stock images of robots, glowing brains, or blue circuit boards. They make a
research page look generic, and reviewers notice.

### Want to change your portrait?

Replace `assets/portrait.jpg` with any **square** image (800x800 or larger works best).
The current one is your uploaded photo, cropped to a head-and-shoulders square. Keep the
same filename and nothing else needs to change.

---

## Edit these before you share the link

Search `index.html` for:

1. **`PASTE_SCHOLAR_URL`** - a commented-out Google Scholar link in the contact card.
   Paste your profile URL and remove the `<!--` and `-->` around that line.
2. **`PASTE_PDF_URL` / `PASTE_CODE_URL`** - a commented-out links row under the BMVC
   paper. Uncomment once the paper and code are online.
3. **"Prize, 3-Minute Research Presentation"** - replace with the exact award name from
   the Energy and AI symposium.
4. **"Last updated August 2026"** in the footer.

---

## Keeping it current

- **New paper:** copy an existing `<li class="pub">` block, update the text, bump the
  `01` / `02` numbers, and pick a colour (`var(--violet)`, `var(--teal)`, `var(--rose)`,
  `var(--indigo)`, `var(--amber)`, `var(--sky)`).
- **New award:** copy an `<article class="award">` block.
- **New CV:** replace `assets/Parinita_Nema_CV.pdf`, keeping the filename.
- **Stat numbers** in the hero (4 Publications, 6 Semesters TA, ...) are plain text - edit
  them directly.

## About the feature-space figure

The scatter plot in the Research section is a feature space where each cluster is one of
your papers, arriving in publication order - clusters that arrived earlier stay exactly
where they are as new ones appear. The stars are class prototypes.

Hover a legend entry to highlight its cluster; click to jump to that paper. Hover a paper
and its cluster lights up. It stops animating for visitors who have asked their system
for reduced motion.

To add a fifth paper to the plot, add one entry to the `CLASSES` array in the script at
the bottom of `index.html`.
