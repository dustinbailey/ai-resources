---
name: ai-writing-audit
description: >
  Clean up or audit any external-facing draft for AI-generated writing patterns. Default is clean-up mode: return the fixed text, no report. Audit mode (each violation quoted with a concrete fix) runs only when the user asks for an audit. Use when checking whether writing sounds like AI, humanizing AI-generated text, or doing an editorial pass on anything a reader outside your business will see: emails, newsletters, LinkedIn posts, investor updates, sales emails and texts, deal promos, web page copy, and UI text. Run it on drafts BEFORE showing them to the user, not only when asked. Trigger on: "does this sound like AI", "audit this draft", "check this for AI", "flag the AI patterns", "make this sound human", "humanize this", "clean this up", "is this too AI-sounding", or when the user pastes copy and asks "how's this" or "what do you think" in a writing context.
---

# AI Writing Audit

Find the tells that make writing read as AI-generated and fix them. Two modes: clean-up (the default) hands back the fixed draft; audit quotes every problem passage with a fix.

Version 1.0 (2026-10-02). Source and updates: https://github.com/dustinbailey/ai-resources/tree/main/ai-writing-audit

## When invoked

The user provides text: pasted in chat, in a file, or by reference. If the text is missing or ambiguous, ask for it before starting.

## Modes

- **Clean-up (default).** Fix every violation and return the cleaned text. No report, no list of changes, no summary of what was fixed. Use this whenever you run the skill on your own draft before showing it to the user, and whenever the user asks to clean up, humanize, or fix a draft.
- **Audit (only on request).** Use when the user explicitly asks to audit, flag, or explain what's wrong: "audit this," "does this sound like AI," "what's wrong with this," "flag the AI patterns." Produce the report in the format below, then offer the rewrite.

**Never fix claim problems silently, in either mode.** Issues from the domain layer (a wrong tax or mechanics statement, numbers that don't add up, a claim with no source) change what the draft says, not how it sounds. In clean-up mode, list them in a short **Check before sending** note under the cleaned text instead of rewriting the claim. Do the same for any style problem that can't be fixed without changing the meaning.

## Process

1. **Load the pattern catalog.** Read `references/ai-pattern-catalog.md` before starting and apply every pattern in it to the draft.

2. **Check for chatbot residue** (in addition to the catalog):
   - Language aimed at the chat interface, not the reader: "I hope this helps," "let me know if you have questions," "feel free to ask," "Certainly!" / "Absolutely!" / "Of course!" as openers.
   - Hedging when the facts are clear: "tends to," "appears to," "seems to." Assert instead.
   - Knowledge disclaimers: "as of [date]," "based on available information," "to the best of my knowledge."
   - For emails: the subject line and sign-off should read like a person wrote them, not a template.
   - **Punctuation:** no em dashes (—). Where a dash genuinely fits, use a spaced en dash ( – ), and see the dash-framing entry in the catalog for how sparingly. (This is a house style; change it to match yours.)

3. **Domain gate.** Does the draft make claims about deals, returns, LP/GP mechanics, tax treatment, or investor specifics?
   - **Yes:** load `references/domain-credibility-checks.md` and apply it. It catches stock-market framing bleeding into private investing, unsourced or invented claims, confident falsehoods, and numbers that don't tie out.
   - **No** (a personal email, a scheduling note, general copy): skip it.

4. **Deliver by mode.**
   - **Clean-up:** the cleaned text, then the **Check before sending** note only if there is something in it.
   - **Audit:** the report in the format below, then ask: "Want a full edited version with all of these fixed?"

## Audit report format (audit mode only)

```
## AI Writing Audit

**Overall:** [X issue(s) across Y categor(ies)] | [CLEAN ✓ / NEEDS WORK ⚠️ / MAJOR ISSUES 🚨]
**Domain layer:** [applied – draft makes deal/return/investor claims | skipped – no domain claims]

---

### Issues by category

**[Category name]** – [N] issue(s)

> "[exact offending passage, with enough context to find it]"
↳ Problem: [one sentence, specific to this passage]
↳ Fix: "[the rewritten text]"

[Repeat per issue, per category]

---

### Verdict

[2–3 sentences: where the draft stands, the one or two changes that matter most, and whether it now reads human.]
```

If the draft is clean, say so in one sentence. For long pieces, audit the whole thing; don't sample.

## Tone

Be direct. Quote the passage, name the problem, write the fix. "Consider revising" is not a fix.
