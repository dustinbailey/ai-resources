# AI Writing Audit

A Claude skill that catches the phrases and sentence patterns that make writing sound AI-generated, and rewrites them. I run every external draft through it before it goes out: emails, newsletters, LinkedIn posts, investor updates, sales copy, web pages.

The pattern list started as my own notes on what I kept deleting from AI drafts, and it has grown every time I caught a new tell. The catalog now covers more than 20 categories of phrases and sentence structures, most with examples and a fix.

## What’s in this folder

- `ai-writing-audit.zip` – the skill, packaged for upload to the Claude app
- `ai-writing-rules.txt` – the same pattern catalog as a plain text file, for ChatGPT, Gemini, and other apps
- `ai-writing-audit/SKILL.md` – the instructions Claude follows when it uses the skill
- `ai-writing-audit/references/ai-pattern-catalog.md` – the pattern catalog. If you only read one file, read this one.
- `ai-writing-audit/references/domain-credibility-checks.md` – an extra layer for writing about private investments (real estate syndication, LP/GP mechanics, returns, tax). Claude only loads it when a draft makes those kinds of claims.
- `CHANGELOG.md` – what changed in each version

## Install

**Claude app (web, desktop, or Cowork)**

1. Download `ai-writing-audit.zip` from this folder: click the file name, then the download button (the arrow icon on the right).
2. In Claude, open Settings → Capabilities and make sure “Code execution and file creation” is on.
3. Go to Customize → Skills, click **+**, choose **Upload a skill**, and select the zip. Don’t unzip it first.

The skill then works in both regular chats and Cowork. ([Anthropic’s instructions](https://support.claude.com/en/articles/12512180-use-skills-in-claude))

**Claude Code, Hermes, OpenClaw, or another AI agent that uses skills**

Paste this into a session:

```
Install the AI Writing Audit skill from https://github.com/dustinbailey/ai-resources. Copy the ai-writing-audit/ai-writing-audit folder (SKILL.md plus its references folder) into the folder where you load skills (for Claude Code that's ~/.claude/skills/ai-writing-audit/), replacing any older copy. Then list the installed files and tell me the version line from SKILL.md.
```

Use the same prompt when a new version comes out.

**ChatGPT**

1. Download `ai-writing-rules.txt` from this folder: click the file name, then the download button (the arrow icon on the right).
2. In ChatGPT, create a new Project (in the left sidebar), or open one you already use for writing.
3. Click **Add files** and upload `ai-writing-rules.txt`.
4. Click **Add instructions** and paste this:

```
Before you give me any writing meant for someone else (emails, posts, newsletters, web copy), check it against every rule in ai-writing-rules.txt and fix what you find. Give me the cleaned-up version.
```

Write in chats inside that Project and the rules apply automatically.

**Gemini**

1. Download `ai-writing-rules.txt` as in the ChatGPT steps.
2. In Gemini, open **Gems** in the left menu and click **New Gem**. Name it something like “Writing Editor.”
3. Paste the same instructions from the ChatGPT steps into the Instructions box.
4. Under **Knowledge**, upload `ai-writing-rules.txt`, then save.

Use that Gem whenever you want writing drafted or cleaned up.

## Using it

The skill has two modes.

- **Clean-up** is the default. Ask Claude to write or fix something (“clean this up,” “make this sound human”) and you get back the finished text, with no report attached. If the draft makes a factual claim that looks wrong or unsupported, Claude won’t quietly rewrite it. It adds a short “Check before sending” note so you can decide.
- **Audit** runs when you ask for it: “Audit this,” or “Does this sound like AI?” You get a report that quotes each problem passage, says what’s wrong, and gives the replacement text, then an offer to produce the clean version.

Claude should also use the skill on its own when you ask it to write something for people outside your business.

## Making it yours

- **Change the house style.** The skill bans em dashes outright. If you like them, delete that line in `SKILL.md`.
- **Swap the domain layer.** `domain-credibility-checks.md` covers real estate syndication because that’s the field I write in. If you write about something else, replace the “Syndication Domain Knowledge” section with the facts AI keeps getting wrong in your field, or delete the file and step 3 of `SKILL.md`.
- **Add your own tells.** When you catch AI writing something you hate, add it to the catalog with an example. That’s how this list got built.

## Updates

I keep improving this as I catch new patterns. Each version is logged in `CHANGELOG.md`, and `SKILL.md` carries the version number so you can see which one you have.

## Credits

Most of the catalog comes from my own editing. A handful of entries were adapted from Mitch Harris’s ai-hunter skill, [tropes.fyi](https://tropes.fyi), and [stop-slop](https://github.com/boraoztunc/stop-slop).

Built by [Dustin Bailey](https://www.linkedin.com/in/thedustinbailey/).
