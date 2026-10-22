# Live evidence for PR 446: link clicks in Lavish's annotate mode

Captured against a real Lavish server (`bin/lavish-axi.js` serving `evidence/repro.html`) in headless
Chrome 155, with real trusted mouse events through the DevTools protocol, so the browser performed the
link actions itself.

| Screenshot | What it shows |
| --- | --- |
| `07-evidence-plain-external-link-review-unchanged.png` | After a plain click on the external link: the review still shows the artifact, no annotation card, the frame did not navigate away. |
| `08-evidence-plain-external-link-opened-beside-review.png` | The tab the plain click opened, `https://example.com/lavish-external`. |
| `09-evidence-anchor-scrolls-in-place.png` | After a plain click on the in-page anchor: the artifact scrolled to that section in place, no card. |
| `10-evidence-alt-click-annotates-link.png` | After Alt+click on a link: the `Annotate <a>` card is open on that link and the artifact did not follow it. |
| `11-evidence-cmd-click-review-unchanged.png` | After Cmd+click on the external link: the review is unchanged, the browser opened its own new tab. |
| `12-evidence-cmd-click-opened-new-tab.png` | The tab the Cmd+click opened. |

`evidence/repro.html` is the artifact under test: it holds an in-page anchor, an external link, a link
inside a label, a link inside a `data-lavish-action` element, and a plain div.
