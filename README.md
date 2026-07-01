# slidewright

**An agent skill for building stunning, zero-dependency HTML presentations — with a built-in review loop.**

`slidewright` teaches a coding agent (Claude Code, and other skill-aware agents) to
generate animation-rich 16:9 HTML decks from scratch or from a `.pptx`, guide a
non-designer through visual style discovery, and hand back a single self-contained
`.html` file that runs anywhere. Every generated deck ships with two review
affordances baked in:

- **Inline editing** — press `E`, click any text, edit in place, save.
- **Comment / annotate mode** — press `C`, click any element or select text, leave a
  note; export all notes as one structured Markdown bundle you paste straight back to
  your agent. A self-contained reference implementation lives in
  [`comment-mode.html`](comment-mode.html) — open it in a browser to see it work.

## What's inside

| Path | Purpose |
| ---- | ------- |
| `SKILL.md` | The skill entrypoint: workflow, phases, style discovery. |
| `html-template.md` | HTML/CSS/JS architecture for generated decks. |
| `viewport-base.css` | Mandatory fixed 1920×1080 stage CSS. |
| `animation-patterns.md` | CSS/JS animation reference. |
| `STYLE_PRESETS.md` | Curated visual presets. |
| `bold-template-pack/` | Expressive template design systems (see credits). |
| `comment-mode.html` | Standalone reference implementation of comment mode. |
| `scripts/` | PPTX extraction, PDF export, Vercel deploy helpers. |

## Install

Drop the folder into your agent's skills directory:

```sh
git clone https://github.com/<you>/slidewright.git ~/.claude/skills/slidewright
```

Then invoke it in a skill-aware agent (e.g. `/slidewright` in Claude Code), or just
ask the agent to "build me a presentation" and it will load the skill on its own.

## Credits

This project stands on two excellent MIT-licensed projects, and would not exist
without them:

- **Slide skill & template library** — [**zarazhangrui/beautiful-html-templates**](https://github.com/zarazhangrui/beautiful-html-templates)
  by [Zara Zhang Rui](https://github.com/zarazhangrui). The original "HTML slide
  templates any coding agent can pick from" concept and the bold template pack
  derive from this work.
- **Comment / annotate review loop** — [**kunchenguid/lavish-axi**](https://github.com/kunchenguid/lavish-axi)
  by [Kun Chen](https://github.com/kunchenguid). The point-at-an-element / select-text
  / send-feedback-to-the-agent pattern is adapted from Lavish Editor.

See [NOTICE](NOTICE) for the full attribution and upstream license notices.

## License

[MIT](LICENSE) — same as both upstream projects.
