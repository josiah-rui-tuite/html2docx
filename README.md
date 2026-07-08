# html2docx

Turn any HTML page into a KDP-ready Microsoft Word (`.docx`) manuscript — in a single, self-contained HTML file that runs entirely in your browser.

html2docx faithfully reflects your HTML tags and CSS (including your page's
**print styles**) into a clean, properly-styled DOCX, and exports the figures in
your page as self-contained SVG/PNG. Nothing is uploaded — all conversion happens
locally in your browser.

---

## ✨ Why html2docx

- **One file, zero install** — just open `kdp_maker.html` in a browser. No server,
  no build step, no account.
- **Private by design** — your HTML never leaves your machine. All parsing,
  rasterizing and DOCX packaging run client-side.
- **Faithful HTML + CSS → DOCX** — the page is rendered in a hidden frame and each
  run is styled from its *computed* CSS (bold / italic / underline / strike /
  color / size / alignment / sup-sub), so cascaded styles come through.
- **Print-mode fidelity** — optionally applies your page's `@media print` rules so
  the DOCX matches how the page looks when printed (the readable, KDP-friendly
  state). Elements hidden in print are dropped automatically.
- **Real Word styles, not "all Normal"** — headings map to `Heading 1–6`, and body,
  lists, quotes, code and captions get proper named paragraph styles. Great for a
  clean manuscript, global restyling, and table-of-contents generation.
- **KDP white-background contrast** — body text is normalized to black for print;
  figure text automatically flips to black or white based on its **local
  background**, so labels never blend into dark boxes.
- **Self-contained figure export** — every `<svg>` is inlined with its computed
  styles before export, so downloaded **SVG/PNG** render correctly even when their
  colors came from CSS classes. Choose SVG, PNG, or both; images are bundled as a
  ZIP.
- **Colored callout blocks** — columns / callouts with a colored background are
  reproduced as shaded DOCX blocks (with an adjustable lightness threshold).
- **Code blocks that survive** — `<pre>` line breaks are preserved as real line
  breaks (not collapsed onto one line), in a monospace, shaded style.
- **Book sizes & units** — KDP trim sizes plus common book sizes, with an **inch ⇄ mm** unit switch, per-edge
  margins and a binding gutter.
- **Japanese-first typography** — default body/heading font is **游ゴシック (Yu
  Gothic)**, applied with full East-Asian font mapping so Japanese renders
  correctly (configurable to any font).
- **Live progress** — a progress bar with elapsed seconds and an estimate, so long
  conversions never feel stuck.
- **Trilingual UI** — English (default), Japanese, 中文. Your choice is remembered.

---

## 🚀 Getting Started

1. Download `index.html`.

or

Visit the [GitHub Pages version](https://josiah-rui-tuite.github.io/html2docx/)


2. Open it in a modern browser (Chrome, Edge, Firefox, Safari).
   > An internet connection is required the first time, because two small
   > libraries are loaded from a CDN (see [Requirements](#-requirements)).
3. **1. Input HTML** — click *Choose HTML file* and pick your `.html` file.
4. **2. Settings** — pick export formats, trim size/unit, fonts, and toggles.
5. **3. Run**
   - *Convert & download DOCX* → `kdp_output.docx`
   - *Export SVG images (zip)* → `svg_export.zip`
6. Open the DOCX in Word and upload to KDP.

---

## ⚙️ Settings reference

**SVG image export**
- Export format: SVG (vector), PNG (raster), or both.
- PNG resolution scale (1×–8×; 2–3× ≈ 300 dpi for KDP).

**DOCX conversion**
- Apply the page's print styles (`@media print`) — recommended for KDP.
- Embed images in DOCX (as PNG).
- Page break before `h1` (KDP chapter break).
- Body text black for contrast (white background).
- Fix low-contrast colors in figures (background-aware black/white).
- Keep colored-background blocks (columns/callouts) — with a background lightness
  threshold (relative luminance 0–1; lighter backgrounds are treated as plain).
- Max image width.

**Trim size & page**
- Unit: inch / mm (converts the numeric fields).
- Trim size: KDP sizes, ISO/JIS (A6–A4, B6, B5), Japanese book sizes, custom, or
  "don't set".
- Margins (top / bottom / inside / outside) and gutter.
- Base font (body & headings), default 游ゴシック.

---

## 📋 Requirements

- A modern, evergreen browser.
- Internet access on first load — html2docx loads two libraries from unpkg:
  - [`docx`](https://github.com/dolanmiu/docx) 8.5.0 — builds the `.docx`.
  - [`JSZip`](https://github.com/Stuk/jszip) 3.10.1 — zips the exported figures.
- See [`THIRD_PARTY_LICENSES.md`](THIRD_PARTY_LICENSES.md) for details. To run
  fully offline, vendor those two files locally and update the two `<script>` tags.

---

## ⚠️ Limitations

- **Layout is paragraph-based.** DOCX has no true multi-column / flexbox / grid
  layout, so complex CSS layouts are approximated in reading order, not pixel
  reproduced.
- **No font embedding.** Fonts are referenced by name; the actual glyphs depend on
  the fonts installed where the DOCX is opened. (KDP recommends standard fonts.)
- **Remote images may be blocked.** Images from another origin without CORS headers
  cannot be rasterized (browser security); a placeholder is inserted and the log
  reports it.
- Figures are embedded in DOCX as PNG (DOCX cannot embed live SVG reliably); the
  original SVG is still available via the separate SVG export.

---

## 🔒 Privacy

All processing is local to your browser. Your HTML, images and generated files are
never sent to any server. The only network activity is fetching the two libraries
from the CDN on first load.

---

## 📄 License

Released under the [MIT License](LICENSE). Third-party components are listed in
[`THIRD_PARTY_LICENSES.md`](THIRD_PARTY_LICENSES.md).

---

