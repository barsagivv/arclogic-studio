# ArcLogic Studio — policy pages

The privacy policies and terms for our games, served by GitHub Pages at
<https://barsagivv.github.io/arclogic-studio/>.

This repository is **public on purpose**. Google Play and the App Store require a privacy
policy at a URL that opens for anyone, with no sign-in, and GitHub Pages only serves public
repositories on a free account. Nothing here but static HTML — no game code, no keys.

## Adding a game

One folder per game, one page per document:

    <game-slug>/privacy-policy.html

then add it to `index.html`. The URL a store has been given must never change afterwards, so
pick the folder name once and leave it alone.

## Live URLs

| Game | Privacy policy |
|---|---|
| RailWorld | <https://barsagivv.github.io/arclogic-studio/railworld/privacy-policy.html> |
| Crowd Runner | <https://barsagivv.github.io/crowd-runner-site/privacy-policy.html> (terms: `crowd-runner-site/terms.html`) - its own repo, see below |
| Quack Blast | <https://barsagivv.github.io/arclogic-studio/quack-blast/privacy-policy.html> (terms: `quack-blast/terms.html`) |

Crowd Runner's pages live only in the `crowd-runner-site` repo: the installed app, Google Play
and its AdMob consent message all link there. The copies that used to sit in `crowd-runner/`
here went stale (July text, without the September analytics and purchases sections), so since
2026-10-10 those two files only forward to `crowd-runner-site`. Edit Crowd Runner's policy there,
never here.
