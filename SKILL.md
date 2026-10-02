---
name: ux-copy-reviewer
description: Review and rewrite UI microcopy — buttons, error messages, empty states, confirmation dialogs, form labels, hints, tooltips, onboarding, notifications, and success messages — for clarity, specificity, actionability, concision, consistency, tone, and accessibility, with a one-line reason for every change. Use this skill whenever the user shares interface text, a screenshot, a Figma frame, or a strings file (JSON, CSV) and asks to review copy, improve wording, name a button, fix an error message, write an empty state, or check whether something is clear — even if they never say "UX copy", "UX writing", or "microcopy".
---

# UX Copy Reviewer

Review interface copy the way a senior UX writer would: find what stops users from understanding or acting, fix it, and explain every change. The goal is copy that helps users act, not copy that merely sounds nice. Every suggestion must say what the user gains — knowing what happens next, how to recover, or what a feature does.

## Gather context first

Three things change the right answer, so check for them before reviewing:

1. **Product voice** — a voice guide, a few adjectives (e.g. "friendly, plain, confident"), or examples of copy the team likes.
2. **Audience** — first-time users, experts, a mixed audience; native or non-native readers.
3. **Moment in the journey** — onboarding, a routine task, a failed payment, a destructive action.

Also note, if available: space limits (character counts, button widths, mobile), whether the copy will be translated, and any existing glossary of product terms.

If voice or moment is missing, ask once, briefly. If the user doesn't answer or wants to move fast, proceed with this assumption and state it at the top of the review: `[ASSUMPTION: clear, neutral, friendly voice]`. Never silently guess the job of a button or screen — if a string's purpose is unclear, ask what it does.

For one or two strings with obvious context, skip the questions and answer directly, stating any assumptions inline. Strings on payment, deletion, security, or legal screens always get the full review, however short they are.

## Review process

1. **Inventory the strings.** List every piece of copy with its exact current text, its type (button, error, empty state, confirmation, label, hint, tooltip, notification, success, onboarding), and its location (screen + element).
2. **Check each string against the seven criteria** below.
3. **Apply the rules for its copy type.**
4. **Check consistency across strings.** Flag any action or object named in more than one way, and build a short glossary of preferred terms.
5. **Rewrite what fails.** Give one recommended rewrite. Add one alternative only when the voice or moment is uncertain, and say what it trades off.
6. **Explain each change in one line**, focused on what the user gains.
7. **Leave good copy alone.** Mark strings that pass as **Keep**. Churning copy that already works wastes the team's time and erodes trust in the review.

## The seven criteria

| Criterion | Question to ask | Common failure |
|---|---|---|
| Clarity | Would a first-time user understand it without context? | Jargon, internal terms, abbreviations |
| Specificity | Does it say exactly what happens or what went wrong? | "Something went wrong", "Submit", "OK" |
| Actionability | Does the user know what to do next? | Errors with no fix, dead-end empty states |
| Concision | Can words be cut without losing meaning? | "Please note that", "In order to" |
| Consistency | Is each action and object named the same way everywhere? | "Delete" on one screen, "Remove" on another |
| Tone | Does it fit the voice and the emotional moment? | Jokes on an error, blaming the user |
| Accessibility | Does it work for screen readers and non-native readers? | "Click here", meaning carried only by color or icon, idioms |

Every flag must name the criterion it fails and give the reason in one line. "Feels off" is not a flag.

## Rules by copy type

- **Buttons and CTAs** — Verb + object describing the outcome. "Place order", not "Submit". The label should make sense read alone, as screen reader users often hear it that way.
- **Error messages** — Say what happened and how to fix it, in plain language. No blame ("You entered an invalid…"), no error codes as the main message. "Your card was declined. Try another card or contact your bank."
- **Empty states** — Explain why it's empty and offer one clear next step. "No orders yet. Your first order will appear here." + a button.
- **Confirmation dialogs** — The title names the action and its scope; buttons repeat the action, never Yes/No. "Delete 3 files?" → [Delete files] [Cancel]. State consequences if irreversible.
- **Form labels and hints** — The label names the field and stays visible (never placeholder-only). The hint covers format or why the data is needed.
- **Tooltips** — Add information the label doesn't already give. If the tooltip repeats the label, cut it.
- **Success messages** — Confirm what happened, briefly and specifically. "Payment sent to Maria", not "Success!"
- **Notifications** — Lead with what changed and why it matters to the user; make the action obvious.

## Tone by moment

Voice stays constant across the product; tone shifts with the user's state.

| Moment | User's likely state | Tone |
|---|---|---|
| Onboarding, success | Curious, positive | Warm; light personality is fine |
| Routine tasks | Focused | Neutral, brief, out of the way |
| Errors, failed payments | Frustrated or anxious | Calm, direct, no humor, no blame |
| Destructive actions | Cautious | Precise about consequences |
| Money, security, legal | Wary | Plain and serious, no cleverness |

If the user provides a voice guide, follow it, and flag any rewrite where the guide and the moment pull in different directions.

## Guardrails

- **Don't invent product facts.** Never make up delivery times, limits, prices, or policies in a rewrite. Use a placeholder like `[X days]` and list it under open questions.
- **Respect space.** If a rewrite is noticeably longer than the original, check it still fits; give a short version for buttons and mobile.
- **No humor or personality** on errors, warnings, or anything involving money, security, or data loss.
- **Translation-safe copy.** If the copy will be localized, avoid idioms and wordplay, and flag strings built by stitching fragments together.
- **Stay consistent.** Every rewrite must use the glossary's preferred terms.
- **Separate copy issues from design issues.** If the real problem is the UI (e.g. a missing undo), say so in one line rather than trying to fix it with words alone.

## Output format

Use this structure:

**Summary** — One or two sentences on overall copy quality and the biggest pattern to fix. State any assumptions here.

**Review table**

| # | Type | Location | Current | Issue (criterion) | Suggested | Why |
|---|---|---|---|---|---|---|
| 1 | Error | Payment screen | Error 402: Transaction failed | Technical code, no next step (Actionability) | Your card was declined. Try another card or contact your bank. | Says what happened and how to recover |
| 2 | Button | Sign-up form | Submit | Vague outcome (Specificity) | Create account | User knows what the click does |
| 3 | Label | Sign-up form | Email address | — | Keep | Already clear and specific |

**Glossary** — Preferred term → variants to replace (only if inconsistencies were found).

**Voice notes** — Two or three observations on tone, only if the copy drifts from the voice.

**Open questions** — Every assumption and placeholder, so nothing invented ships.

For a single string, skip the table: give the suggested version, the one-line reason, and an alternative only if useful.

After the review, offer to export the rewrites as a strings file (JSON or CSV) for developers.
