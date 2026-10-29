<div align="center">

# PickleBoxer's Claude Code mods and skills

Small mods that put the things you keep checking right above the Claude Code prompt, and skills that change how Claude works.

[![Validate](https://github.com/PickleBoxer/claude-plugins/actions/workflows/validate.yml/badge.svg)](https://github.com/PickleBoxer/claude-plugins/actions/workflows/validate.yml)
![Mods](https://img.shields.io/badge/mods-3-d97757)
![Skills](https://img.shields.io/badge/skills-2-d97757)
![Claude Code](https://img.shields.io/badge/Claude%20Code-v2.1.287%2B-d97757)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE)

</div>

## Install

Add the marketplace once:

```
/plugin marketplace add PickleBoxer/claude-plugins
```

Then install any plugin from it:

```
/plugin install burn@pickleboxer
/plugin install drift@pickleboxer
/plugin install peek@pickleboxer
/plugin install pstack@pickleboxer
/plugin install pickle@pickleboxer
```

Or browse them all with `/plugin`.

## Mods

| Mod | What it shows | Latest |
| --- | --- | --- |
| 🔥 [**burn**](https://github.com/PickleBoxer/burn) | Context, 5 hour and weekly limits, usage credits and spend, with a `/burn` pane for the last 7 days | ![burn](https://img.shields.io/github/v/tag/PickleBoxer/burn?label=&color=d97757) |
| 🌿 [**drift**](https://github.com/PickleBoxer/drift) | Folder, branch, ahead/behind and uncommitted changes, with a `/drift` pane for changes and branches | ![drift](https://img.shields.io/github/v/tag/PickleBoxer/drift?label=&color=d97757) |
| 🖼️ [**peek**](https://github.com/PickleBoxer/peek) | Thumbnails for every image you paste, instead of bare `[Image #1]` tags | ![peek](https://img.shields.io/github/v/tag/PickleBoxer/peek?label=&color=d97757) |

### 🔥 burn

Rate limits, usage credits and spend above the prompt.

<img src="https://raw.githubusercontent.com/PickleBoxer/burn/main/docs/desktop.png" alt="burn in the Claude Desktop app" width="720">

```
 Opus 5.5 › Explore   ◔ 31% ctx 62k/200k   ◑ 59% 5h ↻7m   ◕ 81% 7d ↻8h57m   ● €120.06/120   ≈$3.27 session
```

[Read more](https://github.com/PickleBoxer/burn#readme)

### 🌿 drift

How far your working tree has drifted from the last commit.

<img src="https://raw.githubusercontent.com/PickleBoxer/drift/main/docs/terminal.png" alt="drift's band above the Claude Code prompt" width="720">

```
❐ PickleBoxer/dotfiles   ⎇ main ↑2 ↓1   ± 4 files +83 -1
```

[Read more](https://github.com/PickleBoxer/drift#readme)

### 🖼️ peek

Pasted images as thumbnails above the prompt. Needs a terminal that draws images (Ghostty, kitty, iTerm2 or WezTerm).

<img src="https://raw.githubusercontent.com/PickleBoxer/peek/main/docs/screenshot.png" alt="peek showing two pasted images as tiles above the prompt" width="720">

[Read more](https://github.com/PickleBoxer/peek#readme)

## Skills

| Plugin | What it adds | Latest |
| --- | --- | --- |
| ♛ [**pstack**](https://github.com/PickleBoxer/pstack) | poteto's engineering skills (poteto-mode, how/why, architect, arena, verification and the principles), with a `/poteto` mode toggle and a `/pstack` skills pane | ![pstack](https://img.shields.io/github/v/tag/PickleBoxer/pstack?label=&color=d97757&sort=date) |
| 🥒 [**pickle**](https://github.com/PickleBoxer/pickle) | Engineering workflow skills from Addy Osmani's agent-skills, picked per task by `/pickle:pickle-mode`, with a welcome band and a `/pickle-guide` pane | ![pickle](https://img.shields.io/github/v/tag/PickleBoxer/pickle?label=&color=d97757&sort=date) |

### ♛ pstack

[pstack](https://github.com/cursor/plugins/tree/main/pstack) by Lauren Tan, ported from Cursor and kept in sync with upstream. Every skill is typed-only, so it costs no context until you run one (`/pstack:poteto-mode`, `/pstack:how`, ...). A small mod adapts Cursor's tools and models to Claude Code.

[Read more](https://github.com/PickleBoxer/pstack#readme)

### 🥒 pickle

Engineering workflow skills built on Addy Osmani's [agent-skills](https://github.com/addyosmani/agent-skills), plus skills from pstack and Matt Pocock's skills. Start a task with `/pickle:pickle-mode <task>` and it loads the skills that fit, from spec and planning to review and shipping. A mod adds a welcome band above the prompt, a tip on the first task, a `/pickle:review` suggestion after edits and a `/pickle-guide` pane.

[Read more](https://github.com/PickleBoxer/pickle#readme)

## Updating

Third-party marketplaces don't auto-update by default. Pull the latest versions with:

```
/plugin marketplace update pickleboxer
```

or turn on auto-update for `pickleboxer` in `/plugin` under **Marketplaces**.

## How this repo works

Each plugin lives in its own repository. This one only holds [`.claude-plugin/marketplace.json`](.claude-plugin/marketplace.json), which points at each plugin's `main` branch.

Claude Code installs a new release when the `version` in the mod's `plugin.json` changes, so a release is:

1. Bump `version` in the plugin's `.claude-plugin/plugin.json`.
2. Push to `main` and tag it (`v0.5.1`).

Nothing changes here. CI validates the manifest on every push.

## License

[MIT](LICENSE)
