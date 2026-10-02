# UX Copy Reviewer

A Claude skill that reviews and rewrites interface copy the way a senior UX writer would. It finds what stops users from understanding or acting, fixes it, and explains every change in one line.

Share a screenshot, a Figma frame, pasted strings, or a strings file, and get back a clear review table with suggested rewrites, a terminology glossary, and open questions — not vague advice like "make it clearer."

---

## What it reviews

- Buttons and CTAs
- Error messages
- Empty states
- Confirmation dialogs
- Form labels and hints
- Tooltips
- Success messages
- Notifications and onboarding copy

## How it works

1. **Gathers context** — product voice, audience, and where the user is in the journey. If anything is missing, it asks once, or proceeds with a clearly labelled assumption.
2. **Inventories every string** — exact text, copy type, and location.
3. **Checks each string against seven criteria** — clarity, specificity, actionability, concision, consistency, tone, and accessibility.
4. **Applies rules for each copy type** — for example, buttons use verb + object, and confirmation dialogs never use Yes/No.
5. **Checks consistency across screens** — and builds a glossary of preferred terms.
6. **Rewrites what fails, keeps what works** — every change comes with a one-line reason focused on what the user gains.

## Before and after

| Type | Before | After | Why |
|---|---|---|---|
| Error | Error 402: Transaction failed | Your card was declined. Try another card or contact your bank. | Says what happened and how to recover |
| Button | Submit | Create account | User knows exactly what the click does |
| Empty state | Nothing here | No orders yet. Your first order will appear here. | Explains why it's empty and what comes next |
| Confirmation | Are you sure? [Yes] [No] | Delete 3 files? [Delete files] [Cancel] | Buttons name the action, so no one deletes by accident |
| Success | Success! | Payment sent to Maria | Confirms exactly what happened |

## What makes it different

- **Leaves good copy alone.** Strings that already work are marked **Keep**, so reviews don't churn copy for no reason.
- **Never invents product facts.** If a rewrite needs a detail it doesn't know, such as a delivery time, it uses a placeholder like `[X days]` and lists it under open questions.
- **Matches tone to the moment.** Warm on onboarding, calm and direct on errors, serious on anything involving money, security, or data loss.
- **Flags design problems honestly.** If the real fix is in the UI (like a missing undo), it says so instead of trying to solve it with words.
- **Translation-aware.** Flags idioms, wordplay, and fragment-built strings when copy will be localized.

---

## Installation

### Claude.ai

Custom skills on claude.ai require a paid plan (Pro, Max, Team, or Enterprise) with code execution enabled.

1. Download the `ux-copy-reviewer` folder from this repository.
2. Zip the folder. The zip should contain the `ux-copy-reviewer` folder itself, with `SKILL.md` inside it.
3. In Claude, open **Settings**, find **Skills**, and upload the zip.
4. Make sure the skill is toggled on.

### Claude Code

Copy the skill folder into your skills directory:

```bash
# Personal install (available in all projects)
cp -r ux-copy-reviewer ~/.claude/skills/

# Project install (this repo only)
cp -r ux-copy-reviewer .claude/skills/
```

> Skills don't sync between Claude.ai and Claude Code. Install it in each place you want to use it.

---

## Usage

You don't need special commands. Just ask naturally:

- "Review the copy on this checkout screen" *(with a screenshot)*
- "What should this button say?"
- "Fix this error message: Something went wrong"
- "Write an empty state for a saved-items page"
- "Check this strings file for inconsistent terms"

For better results, tell Claude:

- **Your product voice** — e.g. "friendly, plain, confident" or attach a voice guide
- **Who the users are** — e.g. first-time shoppers, IT admins
- **The moment** — e.g. a failed payment, onboarding, deleting an account
- **Any space limits** — e.g. "buttons max 20 characters"

## Output

Every full review includes:

1. **Summary** — overall quality and the biggest pattern to fix
2. **Review table** — type, location, current text, issue, suggestion, and reason
3. **Glossary** — preferred terms and the variants to replace
4. **Voice notes** — tone observations, if the copy drifts from the voice
5. **Open questions** — every assumption and placeholder, so nothing invented ships

For a single string, you get a quick answer: the suggested version, the reason, and an alternative if useful.

---

## Limitations

- A copy review isn't a substitute for testing with real users. Use it to catch clear problems early, then validate key flows with research.
- From a static screenshot, the skill can't see what happens after a click, so it may ask what a button does.
- Rewrites follow general UX writing principles unless you provide your own voice guide.

## Folder structure

```
ux-copy-reviewer/
├── SKILL.md    # The skill instructions Claude follows
└── README.md   # This file
```

## Contributing

Suggestions are welcome. Open an issue with:

- The copy you reviewed (remove anything confidential)
- What the skill suggested
- What you expected instead

## License

MIT — free to use, adapt, and share. See [LICENSE](../LICENSE).

---

Created by Lalita · [GitHub](https://github.com/your-username) · [LinkedIn](https://linkedin.com/in/your-profile)
