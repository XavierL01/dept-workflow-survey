# HLMIC — Department Workflow & Technology Survey

A multilingual, self-hosted survey form that collects department workflow insights and emails the filled document plus an auto-generated report summary.

**Live:** https://xavierl01.github.io/dept-workflow-survey/

## Features

- **3 languages** — English, Português, Tiếng Việt (auto-detects browser language, remembers the choice)
- **7-step wizard** — progress stepper, animated transitions, keyboard navigation (← →, Ctrl+Enter)
- **Live insights** — auto-detects tools, pain signals, and automation opportunities as respondents type
- **Report summary** — every submission includes a quick-snapshot report (top frustrations, bottlenecks, automation candidates) plus the full filled document
- **Auto-save** — drafts persist in the browser; respondents resume where they left off
- **Review step** — copy or download the report (.txt) before finishing
- **Zero backend** — GitHub Pages hosting + FormSubmit email delivery, no accounts or servers to maintain

## How submissions work

1. A department opens the form link, chooses their language, and completes the wizard.
2. On **Finish & Submit**, the filled document + generated report are emailed to the configured address via [FormSubmit](https://formsubmit.co/).
3. Emails arrive with a subject like `Dept Survey [EN]: Sales — Maria Gomez`.

> **First-use setup:** the first submission triggers a one-time activation email from FormSubmit. Click it once and all future responses arrive automatically.

## Configuration

| Setting | Where | Default |
| --- | --- | --- |
| Recipient email | `fetch('https://formsubmit.co/<your-email>')` in `index.html` | `xavier.lucas@cahubauto.com` |
| Language texts | `I18N` object in `index.html` (en / pt / vi) | — |
| Insight detection terms | `insight_terms` per language in `index.html` | — |
| Required fields | `REQUIRED_BY_STEP` in the script | Department, Name/Role, Q6 |

## Run locally

Serve the folder with any static server:

```bash
npx serve .
# or
python3 -m http.server 8000
```

## Deployment

Hosted on GitHub Pages from the `main` branch root. Push changes to `main` and Pages redeploys automatically.

```bash
git push origin main
```

## License

Proprietary — HLMIC internal use.
