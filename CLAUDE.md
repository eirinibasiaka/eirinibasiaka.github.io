# CLAUDE.md

The public GitHub Pages site behind the games' App Store listings: each game's
privacy policy and support page, the root landing page, and `app-ads.txt`.
App Store Connect and AdMob link to these URLs, so a page that moves or breaks
breaks a live listing.

## Who writes what

The game repositories write this site; nothing here is authored on its own.
A change starts in the game's repository (Bend and Fit keep the source of
their page in `docs/store/`) and lands here as a copy of what the game published.

| Path | Written by | What it is |
|---|---|---|
| `index.html`, `privacy.html` | `~/Code/Sway` | Sway's landing page and privacy policy (the site started with Sway) |
| `app-ads.txt` | `~/Code/Sway` | the AdMob publisher line every game's ads rely on; one line, never per game |
| `bend/` | `~/Code/Bend` | Bend's privacy policy and support page |
| `fit/` | `~/Code/Fit` | Fit's support page and privacy policy |
| `pour/` | `~/Code/Pour` | Pour's privacy policy |

A new game adds its own folder, named after its repository in lower case, with
one commit prefixed with the game (`pour: privacy policy for …`).

## Rules

- Never edit a game's page here without the same change in that game's
  repository; the next copy would undo it.
- `app-ads.txt` changes only when the AdMob account does, and then for every game.
- Lessons about the store pages belong to the game repository that learned
  them (its inbox), not here.

<!-- knowledge:begin v2 -->
## Knowledge

When the moment on a line comes, open its path first: a shelf's `index.md`
(then only the pages you need), the research map, or this repo's own research.
Anything else starts at the hub `/Users/vadion/Code/wiki/index.md` (one line per bundle).
- Before you change a privacy or support page App Store Connect links to → /Users/vadion/Code/wiki/development/ios/release/index.md

Never edit these from here. They are read-only to this repo.

### Lessons learned (write-back)

When you learn something another repo could reuse (a trap, a number, a review
outcome, a pipeline fact), write `docs/wiki-inbox/YYYY-MM-DD-<slug>.md` **in the
repo you are running in**, not here if you run from elsewhere, and commit it:

    ---
    type: report
    status: draft
    title: <one falsifiable sentence>
    description: <what it answers, in one line; not the title again>
    about_repo: <repo the lesson concerns>
    source: { repo: <cwd repo>, sha: <HEAD>, run: <run id or "interactive"> }
    shelf: <a shelf the wiki declares: development/games/zelda-like/combat | agentic/harness | …>
    sources:
      - { id: <short-id>, resource: "<URL, or repo:path@sha>" }
    ---
    Evidence, each claim with its source as a footnote [^<short-id>], then
    "Apply:" (what the next agent should do differently) and "Not known:"
    (what it leaves open).

    [^<short-id>]: <the source's title>

Product-only facts stay in this repo's docs. Do not copy wiki pages into this repo.
<!-- knowledge:end -->
