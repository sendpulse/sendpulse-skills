# Changelog — sendpulse-humanizer-uk

All notable changes to the SendPulse Ukrainian Humanizer skill. Format follows
[Keep a Changelog](https://keepachangelog.com/); versioning follows `vMAJOR.MINOR`
(MAJOR = breaking changes to rules/structure; MINOR = additive rules, references, or fixes).

## [1.1] — 2026-07-23

### Added

- **~50 new calque/russianism pairs** in `references/russianisms.md`, adapted from
  [grayodesa/LT-Ukranian-calques](https://github.com/grayodesa/LT-Ukranian-calques) (CC-BY-4.0),
  itself derived from the [UA-GEC](https://github.com/grammarly/ua-gec) corpus (Grammarly, CC-BY-4.0):
  - a dedicated **«по + давальний» temporal-calque** block (по закінченню → після закінчення / по
    закінченні, and 11 more);
  - 7 more «по»-government pairs (по плану → за планом, по можливості → за можливості, по аналогії з
    → за аналогією з, під авторством → за авторством, …);
  - ~20 lexical/phrasal calques (в першу чергу → передусім, на фоні → на тлі, як тільки → щойно,
    з одного боку, таким чином → отже, скоріше за все → найімовірніше, прийняти міри → вжити заходів,
    приходити до висновку → доходити висновку, приводити до → призводити до, мається на увазі →
    йдеться про, …);
  - lexical russianisms (доктор → лікар, сотовий → мобільний, дійсний → справжній, пару → кілька,
    прийшлось → довелося, робити вигляд → удавати, …);
  - active participle `включаючи` → включно з / зокрема.
- **Punctuation coverage** in pattern 22 (`SKILL.md`): parenthetical words (вставні слова) take
  commas on both sides; strip stray spaces before punctuation. Reflected in the checklist and the
  «по»-scanner (temporal forms).
- **`NOTICE`** file with full attribution and license texts (CC-BY-4.0 for the incorporated data;
  MIT for the skill). A «Джерела» section added to `references/russianisms.md`.

### Attribution / licensing

- Incorporated data is **CC-BY-4.0** (grayodesa/LT-Ukranian-calques → UA-GEC/Grammarly); credited in
  `NOTICE` and `russianisms.md`. No ShareAlike — the skill stays MIT. LGPL-2.1 material from the
  source repo (`reference/official-lt/`) is **not** used or redistributed.

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
