# CLAUDE.md

Privacy policies, terms and store-support pages for Bar Sagiv's mobile games (ArcLogic Studio /
DoublePixel), served by GitHub Pages at <https://barsagivv.github.io/arclogic-studio/>.
Static HTML only: no build step, no dependencies, no tests. What is on `main` is what is live.

Talk to the user in Hebrew. Keep code, file names and commit messages in English.

## Hard rules

- **Never rename or move a published page.** Google Play, the App Store, AdMob consent messages
  and the installed games link to these exact URLs. A new game gets its folder name once.
- **The repo is public on purpose** (the stores need a policy URL anyone can open). Never commit
  keys, tokens, game code, internal notes or anything else that should not be public.
- **Crowd Runner is edited in the `crowd-runner-site` repo, never here.** `crowd-runner/*.html`
  only forward there.
- **A policy must match what the game actually does.** Before changing what a policy says is
  collected, shared, or which SDKs are used (AdMob, Firebase, sign-in, purchases), ask the user;
  don't infer it. The Play Data safety answers in `play-forms/` must agree with the policy.
- Don't touch `app-ads.txt` unless asked: AdMob reads it to authorize ad serving.

## Layout

```
index.html                 studio page, links every game
<game-slug>/privacy-policy.html
<game-slug>/terms.html     where the game has terms
lure-line/index.html       game support page, delete-account.html
railworld/sound-preview.html
play-forms/                Play Console Data safety answers as CSV (see its README)
app-ads.txt                AdMob authorization
```

Games: RailWorld, Crowd Runner (forward only), Quack Blast, Bar Remote, Lure Line.

## Page conventions

Copy an existing page of the same kind (newest: `lure-line/`) rather than writing from scratch.

- One self-contained file: inline `<style>`, no external CSS, fonts or scripts. Colors as
  variables on `:root`; mobile breakpoint at `max-width:560px`.
- Bilingual pages have an English card (`id="en" lang="en" dir="ltr"`) and a Hebrew card
  (`id="he" lang="he" dir="rtl"`) on the same page, linked with `#he` / `#en`. Change both
  languages together; they must say the same thing. Wrap Latin names inside Hebrew text in `<bdi>`.
- Use logical CSS properties (`padding-inline-start`, `inset-inline-end`) so RTL works.
- Update the "Last updated" date (both languages) whenever a policy's content changes.
- Contact address in the footer: barsagivv@gmail.com.

## Adding a game

1. Create `<game-slug>/privacy-policy.html` (and `terms.html` if needed).
2. Add the game to `index.html` (name, package id, links) and to the Live URLs table in `README.md`.
3. If it is on Google Play, add its Data safety CSV to `play-forms/` and note it in that README.

## Checking a change

There is no test suite. Before committing, open the changed page in the browser (Chromium via
Playwright is available) at phone and desktop width, in both languages, and check every link.

## Commits

Short English subject that names the game and what changed, e.g.
`Lure Line privacy: Google sign-in on iPhone too`.
