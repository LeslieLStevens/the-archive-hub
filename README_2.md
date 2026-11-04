# The Archive — Hub

Case-file hub for The Archive with Leslie L. Stevens. One page per subject,
gathering the film, the written entry, the Shorts, and the records behind them.

Plain HTML and CSS. No framework, no build step. Hosted on Netlify from this
repository.

## Files

| File | What it is |
| --- | --- |
| `index.html` | Home — the entries index |
| `case.html` | A case page. Copy it for each new entry. |
| `styles.css` | The whole look. Every color is a named variable at the top. |
| `netlify.toml` | Tells Netlify to publish from the top of the repo |

## House design system

These values are fixed. Do not substitute, extend, or add colors. They live in
`:root` at the top of `styles.css`.

| Token | Value | Use |
| --- | --- | --- |
| `--ground` | `#F3EEE5` | The page |
| `--ink` | `#15181B` | Names, titles, body |
| `--ink-muted` | `#5C6166` | Labels, captions, secondary lines |
| `--accent` | `#6E1F2B` | Oxblood — the signature bar only |
| `--hairline` | `#DDD8CC` | 1px dividers between rows |
| `--image-well` | `#E6E0D4` | Only where a real picture will sit |
| `--film-well` | `#15181B` | Only the video embed |

Seven colors. That is the whole palette. Nothing in the stylesheet uses a
hex value outside this block — if you ever need a lighter or darker shade,
reach for an opacity on an existing token rather than adding an eighth color.

Type, from Google Fonts:

- **Bodoni Moda** — names, titles, the wordmark
- **Newsreader** — the finding sentence and all prose
- **Source Sans 3** — labels, 600 weight, caps, letter-spacing 0.24em

## Rules, in order of importance

1. **No cards.** No tinted box around content, ever. Structure comes from a 2px
   ink rule heading each section, a small caps label above it, and 1px hairlines
   between rows. This rule is not negotiable.
2. **Square.** Zero border radius on everything.
3. **The signature bar:** 56 x 3px oxblood, under a name or entry title.
4. **The name is the largest thing on any page.**
5. **The finding** — one flat sentence naming what the record got wrong — is the
   largest text after the title, larger than the entry title in a list.
6. No generated imagery, no stock photography, no desert or Texas motifs.

### Where rules 4 and 5 meet

They pull against each other inside a list row, so the stylesheet settles it
this way:

- **Page level, rule 4 wins.** The largest thing on the home page is the latest
  entry title (64px). The largest thing on a case page is the case title (72px).
- **Inside an earlier-entry row, rule 5 wins.** The finding (30px) is set larger
  than that row's entry title (26px), because the finding is the line a stranger
  repeats to a friend.

To flip it, swap those two `font-size` values in the
`--- Home: earlier entries ---` block of `styles.css`, and again in the phone
block at the bottom. Two lines in each place, nothing else moves.

## Adding an entry

1. Copy `case.html` to a new file, e.g. `more-than-a-signature.html`.
2. Fill in every bracketed placeholder.
3. To embed the film, delete the `<div class="film-placeholder">` block and
   paste the YouTube iframe in its place.
4. Add a row to the earlier-entries list in `index.html`, pointing at the new
   file, and move the previous entry down.

## Adding a record

In `case.html`, copy a `.record-row` block. For a document that should exist and
does not, add the `record-row--absent` class and change the label to NOT HELD.

An absence is a finding and gets the same layout and weight as a document in
hand — marked by an oxblood rule, never by a fill.

## Editorial rules

Binding on everything published here.

- Nothing invented. Nothing composited.
- Every claim traces to a document.
- No generated likeness of any real person.
- Titles and framing are about the person, not the agencies.
- State the fact at its full size and put no adjective near it.

## Contact

hello@leslielstevens.net
