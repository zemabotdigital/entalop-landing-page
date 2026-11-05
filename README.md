# ENTALOP — Landing Page

Single-file landing page for the ENTALOP funnel:

1. **Free 2-hour live call** — the only entry point. Covers competitor analysis
   with Claude, self-reliance with AI, where time and money leak, a plain-language
   map of the AI era, and what is actually useful for the visitor's business.
2. **Qualify inside the call.**
3. **Private invite link** to the 7-Day AI Business Transformation Program.

The 7-day program cannot be booked from the page — the invite comes out of the call.
A "Should you join this program?" section states the filter plainly before anyone books.

## Run locally

```bash
python3 -m http.server 4173
# http://127.0.0.1:4173
```

Matches `.claude/launch.json`.

## Structure

Everything is in `index.html` — markup, CSS and JS, no build step and no dependencies
beyond the Google Fonts stylesheet.

| Section | Anchor |
|---|---|
| Hero + booking form | `#register` |
| The free 2-hour call | `#call` |
| What you learn | `#pillars` |
| 7-day curriculum (invite-only) | `#curriculum` |
| AI tools | `#tools` |
| Industries | `#industries` |
| Host | `#host` |
| Should you join | `#fit` |
| FAQ | `#faq` |

## Configuration

Edit the `CONFIG` object near the bottom of `index.html`:

- `sessionStart` — ISO datetime of the next free call. `null` gives a rolling
  3-day countdown and "Date to be announced".
- `seatsTotal` / `seatsTaken` — the seats bar for the call.
- `logoFile` — set to `assets/entalop-logo.png` to replace the inline SVG mark.

## Before launch

- [ ] Connect the form to a real backend. The submit handler in `index.html` is a
      stubbed `setTimeout`; the POST target is marked with a comment.
- [ ] Set `sessionStart` to the real call date.
- [ ] Add `assets/host.jpg` (the page falls back to a placeholder without it).
- [ ] Replace or remove the placeholder testimonials — they are flagged in an
      HTML comment and currently describe the 7-day program, which is invite-only.
