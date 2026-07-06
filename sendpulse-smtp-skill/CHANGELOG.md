# Changelog

All notable changes to the SendPulse SMTP Skill. Format follows
[Keep a Changelog](https://keepachangelog.com/); versioning follows
[SemVer](https://semver.org/).

## [1.1.0] — 2026-07-06

### Changed

- Authorization: the **Single API Key** (*Settings → API → API keys*, long-lived
  Bearer) is now the preferred method; OAuth client credentials remains the
  alternative. Updated SKILL.md, api-reference, quickstart.
- Product routing now points to the dedicated **`sendpulse-email-skill`** for bulk
  campaigns (address books, segments, analytics) and explicitly names
  **`sendpulse-template-skill`** for building email HTML;
  `references/email-service-api.md` stays as the overview fallback.

## [1.0.0] — 2026-07-06

### Added

- Initial release.
- `SKILL.md` core playbook: product routing (SMTP vs Email Service), prerequisite
  checks, OAuth flow, send rules, hygiene rules, troubleshooting order,
  self-update check.
- References: quickstart, account/sender/DNS setup, full SMTP API reference,
  error & troubleshooting tables, deliverability guide, webhooks guide, SMTP
  relay guide (smtp-pulse.com), Email Service API overview.
- Examples: curl, PHP (SDK + plain cURL), Python (requests), Node.js (fetch),
  plus relay snippets for PHPMailer / nodemailer / smtplib.
- Adapters: Claude Code (native), Cursor rule (.mdc), ChatGPT Custom GPT
  instructions, Gemini GEMINI.md, generic install guide.
