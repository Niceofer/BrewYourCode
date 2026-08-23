# Third-Party Licenses

BrewYourCode bundles open-source components covered by their own licenses.
This file lists the components and the notice obligations they impose on the
BrewYourCode distribution. Each component's own `LICENSE` text — included
inside its npm package and shipped in the application's `resources/` folder
— is the authoritative source.

---

## Bundled components

### Runtime — application

| Package | License |
|---|---|
| Next.js | MIT |
| React, React-DOM | MIT |
| Three.js | MIT |
| `@dimforge/rapier3d-compat` (physics) | Apache-2.0 |
| `@google-cloud/storage` | Apache-2.0 |
| `@huggingface/transformers` (local RAG embeddings) | Apache-2.0 |
| `google-auth-library` (OAuth) | Apache-2.0 |
| `@sparkjsdev/spark` (Gaussian-Splat renderer) | MIT |
| `better-sqlite3` | MIT |
| `diff` | BSD-3-Clause |
| `highlight.js` | BSD-3-Clause |
| `isomorphic-dompurify` (DOMPurify is dual-licensed MPL-2.0 OR Apache-2.0; Apache-2.0 taken) | MIT (wrapper) |
| `marked-highlight` | MIT |
| `socket.io` | MIT |
| `sucrase` (TS transform) | MIT |
| `undici` (Node fetch) | MIT |
| `uuid` | MIT |
| `vectra` | MIT |
| `wink-bm25-text-search` | MIT |
| `electron-updater` | MIT |

### Native image processing

| Package | License |
|---|---|
| `sharp` | Apache-2.0 |
| `libvips` (+ libwebp / libheif via the `@img/sharp-*` native binary) | **LGPL-3.0-or-later** |

See "LGPL-3.0 obligations" below for the rights LGPL grants you and how
BrewYourCode discharges its obligations.

### Build / development

Build-only tooling (Electron, electron-builder, ESLint, TypeScript, etc.) is
not redistributed inside the application. Their licenses (predominantly MIT,
with TypeScript under Apache-2.0) govern only the development workflow.

### Local AI model

| Item | License |
|---|---|
| `Xenova/all-MiniLM-L6-v2` (transformers.js embedding model, when shipped with the app) | Apache-2.0 |

---

## License-class obligations (summary)

For binding terms, refer to each component's own `LICENSE` file.

### MIT
The copyright notice and the MIT permission text are preserved in this
distribution by including each package's `LICENSE` file in the installed
application's resource tree.

### BSD-3-Clause (`diff`, `highlight.js`)
Copyright notice, disclaimer, and license text are preserved. The
non-endorsement clause prohibits using the original authors' names in
marketing without their permission.

### Apache-2.0 (`@dimforge/rapier3d-compat`, `@google-cloud/storage`, `@huggingface/transformers`, `google-auth-library`, …)
Copyright notices are preserved, the `LICENSE` text is shipped, any
upstream `NOTICE` files are reproduced, and Apache's implicit patent
grant applies. Modifications to these components, if any, are marked.

### Apache-2.0 path taken for dual-licensed DOMPurify
DOMPurify is dual-licensed under `(MPL-2.0 OR Apache-2.0)`. BrewYourCode
takes the Apache-2.0 option, so MPL-2.0's source-disclosure obligation
does not attach.

---

## LGPL-3.0 obligations (sharp / libvips)

BrewYourCode uses `sharp` for server-side thumbnail generation. The native
binary `@img/sharp-*` bundles **libvips** (and its transitive `libwebp`,
`libheif`, etc.), which are licensed under **LGPL-3.0-or-later**. LGPL
applies copyleft only to the LGPL-licensed library itself — BrewYourCode's
own code is unaffected.

The LGPL obligations BrewYourCode discharges:

1. **You can replace the LGPL component.**
   The libvips bindings ship as a separate native `.node` dynamic library at
   `node_modules/@img/sharp-*/lib/sharp-*.node` inside the installed
   application. You may replace this file with a build of your own choosing.
   The Terms of Service's reverse-engineering clause expressly does not
   restrict this right (Terms §11).
2. **License text and copyright notice are preserved.**
   sharp's `LICENSE` and `NOTICE` ship inside the package and are included
   in the application bundle. This file additionally records the LGPL use.
3. **Source code is available.**
   - libvips — <https://github.com/libvips/libvips>
   - sharp  — <https://github.com/lovell/sharp>

What BrewYourCode is **not** required to do:

- Release its own source code. LGPL applies only to libvips itself.
- Publish modifications, because BrewYourCode does not modify libvips. If a
  future build did modify it, the modifications would have to be made
  available under LGPL-3.0.

---

## Where to find the bundled `LICENSE` files

The packaged BrewYourCode installer ships each component's own `LICENSE`
file under its `node_modules/<package>/` path inside the application's
`resources/` directory. The bundled set is the authoritative legal text;
this file is a navigation aid.

---

© 2026 VirtualFlow, Inc.
