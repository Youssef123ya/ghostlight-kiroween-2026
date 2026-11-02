# Ghostlight verification

Verified locally on November 2, 2026, using Node.js 24 and the Codex in-app browser.

## Automated checks

`node --test` passes the color numerical tests and real DOM structural/regression tests. Tests cover reference contrast values, alpha composition, normal versus large-text thresholds, name/label handling, hidden content, decorative choices, repair validation, wrapping labels, duplicate IDs, stable issue identity, safe serialization and manual-review fallback for complex backgrounds. Happy DOM is not a rendering-accuracy substitute for a browser.

## Browser workflow

- Original demo: 7 automated findings across 8 focused categories.
- Empty alternative text is rejected unless the decorative option is explicitly selected.
- Decorative choice removes the image finding; Undo restores it.
- Completing all seven guided repairs reaches 0 focused findings and 7 original findings cleared.
- Compare retains the original page and displays the repaired version separately.
- Source contains one doctype, no internal data-gl-id attributes, the safety CSP and the repaired label.
- Empty import is rejected with a visible message.
- Imported test HTML: script elements, onload handlers and remote src attributes were removed; a script execution marker was absent.
- Imported SVG naming repair produced a named image in the browser accessibility tree.
- Alpha text was measured at 1.25:1 in the regression fixture. Gradient and ancestor-opacity cases generated manual-review warnings instead of fabricated ratios.
- At a 390 px viewport, the document width stays within the viewport and the panels stack.

## Remaining limits

No screen-reader user study, exhaustive WCAG audit, cross-browser matrix or public judge-access test is claimed. Those require additional evaluation. The exported page is static and sanitized. Public GitHub, a judge-accessible app URL and the public YouTube video remain submission work.
