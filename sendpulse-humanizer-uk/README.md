# SendPulse Ukrainian Humanizer — `sendpulse-humanizer-uk`

An AI skill that **humanizes and translates text into Ukrainian** so it reads like a native wrote
it — not like machine output. It removes AI-generation markers (officialese, clichés, uniform
rhythm) *and* the Russian trace that machine translation leaves behind (calques, russianisms,
active participles, missing vocative). Works for any content, with a dedicated playbook for **SaaS
UI microcopy**.

> Олюднює й перекладає тексти українською так, щоб вони звучали як жива мова носія. Прибирає ознаки
> нейромережі, канцелярит, русизми, кальки й суржик. Знімає два шари одразу: машинний і російський.

It's a plain folder — `SKILL.md` (instructions) + `references/` (on-demand docs). No installation,
no dependencies, no external tools. Just make it available to your AI assistant.

---

## Why a separate Ukrainian skill

The English [avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing) and the Russian
[humanizer-ru](https://github.com/Vladimir-Human/humanizer-ru) skills catch universal AI markers,
but they miss what makes Ukrainian text read as machine-made. LLMs generate Ukrainian *through*
Russian- and English-biased internal representations, so the output carries a **Russian trace** no
English or Russian humanizer is built to see:

| | sendpulse-humanizer-uk | humanizer-ru | avoid-ai-writing |
|---|---|---|---|
| Target language | Ukrainian | Russian | English |
| Removes russianisms / surzhyk | **Yes (core)** | n/a | n/a |
| Active participles `-учий/-ючий` rule | **Yes** | No | No |
| Preposition «по» calques | **Yes** | No | No |
| Vocative case in address | **Yes** | No | No |
| Feminitives & living morphology | **Yes** | No | No |
| Translate + humanize (RU/EN → UK) | **Yes** | No (translation excluded) | No |
| SaaS UI microcopy playbook | **Yes** | No | No |
| AI-pattern catalog | Yes (33) | Yes (52) | Yes |

For Ukrainian, the strongest "this was written by a machine" signal is not statistics — it's the
Russian trace. A human editor spots «по замовчуванню» or «існуючий клієнт» instantly. This skill
treats that as a top-priority pattern.

---

## What's inside

- **`SKILL.md`** — the core playbook: method, four modes, HARD BANS, a 33-pattern catalog adapted
  for Ukrainian (with the Ukrainian-specific section 14–18), and a "living Ukrainian text" checklist.
- **`references/russianisms.md`** — a large lookup dictionary of russianisms, calques, active
  participles, «по»-calques, UI-specific fixes, "false friends" not to over-correct, and an optional
  purist layer.
- **`references/ui-microcopy.md`** — SaaS UI playbook: standard verbs, tone, buttons, error
  messages, empty states, 3-form pluralization, number/date/currency formats, variables.
- **`references/translation.md`** — RU/EN → natural Ukrainian workflow.
- **`references/detectors.md`** — what AI detectors measure and an honest note on Ukrainian.

---

## Modes

- **Full humanization** (default for Ukrainian text) — the whole catalog + antisurzhyk.
- **Translate + humanize** (source is RU/EN) — translate the *thought*, then apply antisurzhyk and
  the full catalog in one pass.
- **Audit** ("перевір", "знайди AI-маркери") — diagnose only, don't rewrite.
- **Targeted fix** ("прибери суржик", "виправ канцелярит") — one category only.

---

## Install

The skill is just Markdown with no tool dependencies. It works in any AI assistant that reads a
`SKILL.md` (Claude Code/Desktop, Cursor, ChatGPT, and other LLMs).

### Claude Code (CLI / IDE extension)
- **Personal (all projects):** copy the `sendpulse-humanizer-uk/` folder into
  - macOS/Linux: `~/.claude/skills/`
  - Windows: `%USERPROFILE%\.claude\skills\`
- **One project / team (commit to repo):** copy it into `.claude/skills/` in the project.
- The folder name must stay `sendpulse-humanizer-uk`. It loads automatically — just ask to
  "олюдни цей текст українською" or "переклади і олюдни", and the skill triggers.

### Claude.ai / Claude Desktop
- Zip the `sendpulse-humanizer-uk/` folder.
- Settings → **Capabilities → Skills** → **Upload skill** → choose the zip. Enable it.

### Cursor
- Add the `sendpulse-humanizer-uk/` folder to your project.
- Create a project rule (e.g. `.cursor/rules/humanizer-uk.md` or an `AGENTS.md`):
  *"When asked to humanize or translate text into Ukrainian, follow
  `sendpulse-humanizer-uk/SKILL.md` and the files it links in `references/`."*

### ChatGPT
- **Custom GPT (best):** upload `SKILL.md` + the `references/*.md` files as **Knowledge**, and put
  in the instructions: *"Follow SKILL.md and its references to humanize/translate text into
  Ukrainian."*
- **Plain chat:** paste `SKILL.md` (and the relevant `references/*.md`) into the chat, then paste
  your text.

### Other LLMs / agents
- Provide `SKILL.md` (and references) as system prompt / context / knowledge files.

---

## Use

Just ask, in Ukrainian, Russian, or English:

```
Олюдни цей текст: [текст]
Переклади українською природно і олюдни: [RU/EN текст]
Перепиши, звучить як робот: [текст]
Прибери суржик і кальки: [текст]
Перевір на AI-маркери: [текст]   ← audit mode, no rewrite
```

For UI copy, mention it's an interface string ("це кнопка", "текст помилки") so the skill applies
the microcopy rules (standard verbs, length, pluralization).

---

## Keeping it up to date

The skill is versioned (`VERSION` file + `version` in `SKILL.md` frontmatter). With web access, the
assistant may check the published `VERSION` on GitHub once per conversation and tell you if a newer
version exists — it never blocks your task. See `CHANGELOG.md` for version history.

## License

MIT — use freely, fork, improve. See `LICENSE`.
