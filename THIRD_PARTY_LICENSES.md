# Third-Party Licenses

KDP Maker is a single HTML file. It does **not** bundle any third-party code.
At runtime it loads the two libraries below from the unpkg CDN via `<script>`
tags. Their code is fetched by the user's browser and is not redistributed as
part of this repository.

The exact versions and URLs referenced by `kdp_maker.html` are:

| Library | Version | Loaded from | License |
|---------|---------|-------------|---------|
| docx (docx.js) | 8.5.0 | `https://unpkg.com/docx@8.5.0/build/index.umd.js` | MIT |
| JSZip | 3.10.1 | `https://unpkg.com/jszip@3.10.1/dist/jszip.min.js` | MIT OR GPL-3.0 (dual) |

No fonts or other external assets are fetched (the UI uses system fonts). The
`http://www.w3.org/2000/svg` string in the source is an XML namespace, not a
network request.

---

## docx (docx.js)

**License:** MIT License

**Source:** https://github.com/dolanmiu/docx

```
MIT License

Copyright (c) 2016 Dolan

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## JSZip

**License:** Dual licensed — MIT **or** GPL version 3. You may use it under
either license at your choice. This project uses it under the MIT license.

**Source:** https://github.com/Stuk/jszip

```
JSZip is dual licensed. At your choice you may use it under the MIT license
*or* the GPLv3 license.

The MIT License
===============

Copyright (c) 2009-2016 Stuart Knightley, David Duponchel, Franz Buchinger,
António Afonso

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
```

The full text of the GPLv3 alternative is available at
https://www.gnu.org/licenses/gpl-3.0.txt and in the JSZip repository.

---

## Notes on redistribution

- KDP Maker itself is released under the MIT License (see `LICENSE`).
- Because the libraries above are loaded from a CDN and are not included in this
  repository, distributing this repository does not redistribute their code.
- If you choose to vendor these libraries locally (e.g. for fully offline use),
  include the corresponding license text above alongside the copied files. Both
  libraries are redistributable under the MIT terms shown here.
