# Changelog — sendpulse-humanizer-uk

All notable changes to the SendPulse Ukrainian Humanizer skill. Format follows
[Keep a Changelog](https://keepachangelog.com/); versioning follows `vMAJOR.MINOR`
(MAJOR = breaking changes to rules/structure; MINOR = additive rules, references, or fixes).

## [1.0] — 2026-07-22

Initial public release.

### Added

- **Core playbook** (`SKILL.md`): fundamental principle (statistical deviation), what detectors
  measure, four modes (full humanization / **translate + humanize** / audit / targeted fix), text
  classification table (with a dedicated **UI-microcopy** row), A–D priority tiers, a 6-step process
  with a triple-pass audit, and a "living Ukrainian text" checklist.
- **Two-layer model** unique to Ukrainian: strips both the **machine trace** (rhythm, clichés,
  officialese) common to all languages *and* the **Russian trace** (calques, russianisms, active
  participles, missing vocative) specific to Ukrainian machine translation.
- **HARD BANS** in two groups: AI clichés + the most frequent russianism taboos.
- **Pattern catalog** (33 patterns, A–F) adapted for Ukrainian, including the differentiating
  Ukrainian-specific section (14–18): russianisms/surzhyk, active participles `-учий/-ючий`,
  the preposition «по», vocative case, feminitives & living morphology.
- **references/russianisms.md** — a large lookup dictionary: lexical russianisms, active participles,
  «по»-calques, syntactic calques, UI-specific russianisms, "false friends" not to over-correct,
  and an optional purist layer.
- **references/ui-microcopy.md** — SaaS UI playbook: standard verbs, tone/«Ви», buttons, error
  messages, empty states, onboarding, 3-form pluralization, number/date/currency formats, variables.
- **references/translation.md** — RU/EN → natural Ukrainian workflow (translate the thought, not the
  words), translationese removal, glossary discipline, RU→UK and EN→UK pitfall tables.
- **references/detectors.md** — what detectors measure (perplexity, burstiness, sequence statistics),
  an honest note on the sparse state of Ukrainian detection research, and why the Russian trace is
  the strongest "non-human" signal for Ukrainian.
- **Portability**: platform-neutral SKILL.md format that works in Claude Code/Desktop, Cursor,
  ChatGPT, and any LLM. `VERSION` file + "Keeping this skill up to date" self-check + `metadata.homepage`.
