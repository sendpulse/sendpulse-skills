# Changelog

All notable changes to the SendPulse Email Service Skill. Format follows
[Keep a Changelog](https://keepachangelog.com/); versioning follows
[SemVer](https://semver.org/).

## [1.0.0] — 2026-07-06

### Added

- Initial release.
- `SKILL.md` core playbook: three-skill routing (template / SMTP / email service),
  Single API Key auth (OAuth alternative), campaign lifecycle mental model,
  critical rules (Base64 body, verified sender, review expectations, 4/hour limit,
  cost check, tracking), troubleshooting order, self-update check.
- References: quickstart (first campaign), address books & subscribers & variables
  & tags & blacklist, segmentation (presets, conditions, recipes), campaigns
  (create/schedule/statuses/review, A/B, resend to unopened, best time, timezone,
  dynamic lists), analytics playbook with reference ranges, full API reference,
  errors & campaign-status decoder, webhooks (incl. task_status_update),
  list building & hygiene.
- Examples: curl, PHP, Python, Node.js — full lifecycle each (book → subscribers →
  campaign → analytics → suppression), webhook receiver sketches.
- Adapters: Claude Code (native), Cursor rule (.mdc), ChatGPT Custom GPT
  instructions, Gemini GEMINI.md, generic install guide.
