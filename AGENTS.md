# Teldire Campaign - Agent Guidelines

This document captures the conventions, preferences, and standards established for this Obsidian vault. Follow these guidelines when editing or creating any files in this project.

---

## General Writing Rules

- **No em dashes.** Use standard hyphens (`-`) everywhere. Em dashes have been deliberately removed from this project.
- **Past tense throughout session notes.** The narrative should read as "the party discovered" not "the party discovers." Consistency is critical.
- **No fabricated information.** When writing wiki pages, session recaps, or any content, only use information that comes directly from session notes, the Pre-Session 1 Snapshot (Teldire Bible), the Zalros Deep Dive (DM chatlogs), or confirmed in-game events. "Reading between the lines" for obvious emotional beats is fine (e.g., a character being upset after taking a hit), but never invent character hooks, backstory details, or plot points.
- **Tone:** Session notes should be clean, professional, easy to read, and engaging for players. They are written by the campaign's note taker (Daulton, who plays Zalros).

---

## Obsidian Conventions

### Internal Links (`[[]]`)

Only link the following categories. Do NOT over-link - dead links to nonexistent pages are overwhelming.

**Link these:**
- **Player Characters:** `[[Zalros]]`, `[[Shamash]]`, `[[Brog]]`, `[[Elara]]`, `[[Drakka]]`
- **Figurine Companions:** `[[Samwell]]`, `[[Mars]]`, `[[Peridot]]`, `[[Lacey]]`, `[[Artemis]]`, `[[Oswald]]`
- **Named NPCs met in-session:** `[[Chisum]]`, `[[Jarvis]]`, `[[Brog's Mom]]`, and any future NPCs as they appear
- **Cross-file session references:** When linking between session notes (e.g., from a wiki page to a session)

**Do NOT link:**
- Generic locations, items, or lore concepts that don't have their own page yet
- One-off details or things that only appear in a single sentence
- Anything where a dead link would clutter more than it helps

**For locations:** Instead of wiki-linking to a page, use block ID links (`[[#^block-id|Display Text]]`) that jump to where the location was visited within the session notes. This is more useful than a dead page link.

### Block IDs (`^block-id`)

Block IDs are used extensively in session notes to create "bookmarks" that can be linked to from loot sections, revisit lists, location references, and wiki pages.

- Place the `^block-id` on its own line directly after the paragraph it marks
- Use lowercase with hyphens: `^longsword-found`, `^chisum-met`, `^coffin-cliffhanger`
- Key places to add block IDs: loot discoveries, NPC introductions, location arrivals, cliffhangers, notable losses, plot hooks

### Tags (`#`)

Used sparingly and consistently:
- `#plot-hook` - Unresolved story threads
- `#loot` - Items found or purchased
- `#session`, `#combat`, `#social` - In frontmatter for session categorization
- Character class/race tags in wiki page frontmatter (e.g., `#PC`, `#warlock`, `#human`)

### Callouts

Use Obsidian callout syntax for key moments in session notes:
- `> [!tip] Loot Acquired` - When items are found
- `> [!danger] Notable Loss` - When items are destroyed or lost
- `> [!info] Lore Drop` - Important world/character lore revealed
- `> [!warning] Cliffhanger` - Session-ending or major dramatic moments
- `> [!quote] Memorable Quote` - Funny or significant in-character quotes

### Images

Character photos are stored in `Character Photos/` with subfolders for PCs, NPCs, and Figurine Companions. Embed in wiki pages with: `![[CharacterName.png|250]]`

### Aliased Links in Tables

**Do NOT use aliased links (`[[link|text]]`) inside markdown tables.** The `|` in the link conflicts with table cell separators and Obsidian's linter will break them. Use bullet lists instead for any section that needs aliased links.

---

## Session Note Structure

Every session note should follow this template:

```markdown
---
tags:
  - session
  - combat (if applicable)
  - social (if applicable)
session: [number]
date: [YYYY-MM-DD]
---

# Session [N] - [Title]

## Main Session Notes

[Narrative paragraphs with block IDs on key moments]

---
## Some Things to Potentially Revisit Later

- **Hook name** - Description ([[#^block-id|Jump to scene]]) #plot-hook

---
## Key Loot / Items

- **Item name** - Description ([[#^block-id|Where we found it]]) #loot

---
## Notable Losses This Session

- **Item name** - How it was lost ([[#^block-id|Where it happened]])

---
## Locations Visited This Session

- **Location Name** - [[#^block-id-1|First visit]] / [[#^block-id-2|Second visit]]

---
## Next Session Recap

[2-3 paragraph narrator-style recap meant to be read aloud at the table. Should flow like "On the last episode of..." energy - building from action, through lighter moments, ending on the cliffhanger. Only cover what's relevant to the upcoming session's direction.]
```

---

## Character Wiki Page Structure

Every PC wiki page follows this template (see `Characters/Zalros.md` as the gold standard):

```markdown
---
tags:
  - PC
  - [class]
  - [race]
aliases:
  - [Full Name]
---

# [Full Name]

![[CharacterName.png|250]]

---
## Table of Contents

> [[#At a Glance]]
> [[#Personality]]
> [[#Backstory]]
> [any character-specific sections]
> [[#Pre-Campaign Connections]]
> [[#Abilities & Magic]]
> [[#Session Appearances]]
> [[#Current Goals (Post-Session N)]]

---
## At a Glance

[Right-aligned label table with Race, Class, Background, Age, Height/Weight, etc.]

---
## Personality
## Backstory
## [Character-specific sections as needed]
## Pre-Campaign Connections
## Abilities & Magic
## Session Appearances

### Pre-Campaign Sessions (Warmup Arc)
[Events from the initial warmup/test sessions before the "real" campaign]
[Flashback moments marked with bold **Flashback:** prefix]

### Session 1 - [[Session 1 - Of Marrow & Maple|Of Marrow & Maple]]
### Session 2 - [[Session 2 - Mutual Ache for Something More|Mutual Ache for Something More]]
[Continue for each session]

---
## Current Goals (Post-Session N)
```

**Important:** If information is unknown for a section, include the section header anyway with italicized placeholder text like `*Needs more info - ask the player!*`. This highlights gaps to fill in later.

---

## Session Numbering

The campaign has two sets of session numbers:
- **Pre-Campaign Sessions (1-3):** Warmup/test sessions documented in the Pre-Session 1 Snapshot file. These include the demiplane, Miragryx, the flashback montage, meeting Samwell, etc.
- **Real Sessions (1+):** The "official" campaign sessions. Session 1 is "Of Marrow & Maple," Session 2 is "Mutual Ache for Something More," etc.

In wiki pages and all references, the Pre-Campaign sessions are grouped under "Pre-Campaign Sessions (Warmup Arc)" and the real sessions use their proper titles and numbers.

---

## Git Workflow

- **Default branch:** `main`
- **Feature branches:** Used for batches of changes (e.g., `session-2-polish`, `obsidian-tips-example`)
- **Obsidian-git plugin:** Installed for in-app git operations
- **Remote:** `https://github.com/Git-Daulton/teldire-campaign`

---

## Vault Folder Structure

```
Teldire Campaign/
  Characters/          - PC wiki pages (Zalros.md, Shamash.md, etc.)
  Character Lore/      - Deep dives and DM chatlogs
  Character Photos/
    PCs/               - Player character portraits
    NPCs/              - NPC portraits
    Figurine Companions/ - Companion portraits
  Session Notes/       - All session markdown files
  [Root files]         - Pre-Session 1 Snapshot, Obsidian Tips, etc.
```

---

## Next Session Recap Guidelines

The recap is read aloud at the table to start each session. It should:
- Be 2-3 paragraphs, written in a narrator voice
- Flow naturally when spoken - no awkward phrasing or overly complex sentences
- Build from action recap → lighter/social moments → end on the cliffhanger
- Only include what's relevant to the direction of the upcoming session
- Can reference major unresolved hooks from previous sessions if relevant
- Should NOT include things the party won't revisit in the upcoming session (e.g., don't mention the teleportation circle if next session is social RP)
