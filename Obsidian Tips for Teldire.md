# Obsidian Tips for Your Campaign Notes

This file is a guide to using Obsidian more effectively for your Teldire campaign. Below are practical tips with real examples pulled straight from your Session 1 and Session 2 notes. Feel free to delete this file once you've absorbed the ideas!

---

## 1. Internal Links (`[[]]`) - The Bread and Butter

This is the single most powerful Obsidian feature. Wrapping a name or term in `[[double brackets]]` creates a clickable link. If the target page doesn't exist yet, Obsidian shows it in a lighter color - clicking it auto-creates the page. This is how you build a living wiki over time.

**In your current notes, you write:**
> Shamash fired a Ray of Frost at the Helmed Horror before making a decisive critical blow against the beast.

**With links, it becomes:**
> [[Shamash]] fired a Ray of Frost at the [[Helmed Horror]] before making a decisive critical blow against the beast.

Now "Shamash" is clickable and leads to a dedicated page where you could track his stats, backstory, and key moments. "Helmed Horror" could link to a short page describing what the party knows about these constructs.

### What to link (and what not to)

**Great candidates for links:**
- **PCs:** `[[Zalros]]`, `[[Elara]]`, `[[Brog]]`, `[[Shamash]]`, `[[Drakka]]`
- **Recurring NPCs:** `[[Samwell]]`, `[[Jarvis]]`, `[[Chisum]]`, `[[Rosetta]]`, `[[Vesamear Fig]]`
- **Locations:** `[[Gosslupe]]`, `[[Samwell's Tower]]`, `[[The Kiln]]`
- **Important items:** `[[Longsword +3]]`, `[[Gem of Brightness]]`, `[[Jarvis' Calling Stone]]`
- **Lore concepts:** `[[The Jeering Sparrow]]`, `[[Skeleton Crew]]`, `[[The Kiln]]`

**Don't bother linking:**
- Generic things like "hallway", "door", "chest"
- One-off details that won't come up again
- Things that only appear in a single sentence and have no further context

### Display Name Aliases

Sometimes you want the link to say something different than the page name:
```
[[Zalros|Zalros Mi'hen]] studied the teleportation circle.
[[Gosslupe|Gosslupe City]] buzzed with activity.
```
This links to the `Zalros` page but displays as "Zalros Mi'hen" in your text.

---

## 2. Tags (`#`) - Categorize Without Creating Pages

Tags are lightweight labels. They don't create pages - they just let you search and filter. You add them inline or in a frontmatter block at the top of a file.

### Inline tags (anywhere in your text)

At the end of a paragraph or section, drop a tag:
> Brog purchased a truffle-hunting pig for his farm. #shopping #Brog

### Frontmatter tags (top of the file)

At the very top of a session file, you can add a YAML block:
```yaml
---
tags:
  - session
  - combat
  - social
  - gosslupe
session: 2
date: 2026-03-18
---
```

### Suggested tag system for your campaign

| Tag | Use it for |
|---|---|
| `#session` | All session notes |
| `#combat` | Sessions or sections with combat |
| `#social` | Sessions or sections with RP/shopping |
| `#plot-hook` | Unresolved story threads |
| `#loot` | Items found or purchased |
| `#PC/Zalros`, `#PC/Brog`, etc. | Moments featuring a specific PC heavily |
| `#NPC` | Sections introducing or featuring NPCs |
| `#location/gosslupe` | Scenes in a specific place |

You can then search for any tag using the search panel (`Ctrl+Shift+F`) or by clicking any tag in your notes.

---

## 3. Headers (`#`, `##`, `###`) - Structure Your Sessions

You're already using `#` headers, which is great! Here's a structure that would work well for every session going forward:

```markdown
---
tags:
  - session
  - combat
  - social
session: 3
---

# Session 3 - [Title Here]

## Main Session Notes

[Your narrative goes here, broken into paragraphs as you already do]

## Some Things to Potentially Revisit Later

- **Hook name** - Description

## Key Loot / Items

- **Item** - Description

## Notable Losses This Session

- **Item** - How it was lost

## Next Session Recap

[Your narrator-style read-aloud recap]
```

The key benefit: Obsidian's **Outline** panel (right sidebar, looks like a bullet list icon) will show all your headers as a clickable table of contents. Super handy for jumping around a long session file.

---

## 4. Callouts - Highlight Important Moments

Obsidian supports styled callout boxes. You're already using `>` blockquotes for item descriptions (great instinct!), but callouts take it further:

```markdown
> [!warning] Cliffhanger
> A coffin Rosetta specifically traveled to acquire began violently shaking,
> shed its chains, and cracked open at center stage.

> [!tip] Loot Acquired
> **Longsword +3** - Three gem slots, requires attunement.

> [!info] Lore Drop
> The Kiln is a colossal, wandering golem made by giants that houses the
> Temple of the Jeering Sparrow at its heart.

> [!danger] Notable Loss
> **Scroll of the Three Principles** - Destroyed. Natural 1. Gone forever.

> [!quote] Memorable Quote
> "Try all you want, but that wizard made us immortal so we'd be ants forever!"
```

These render as colored, collapsible boxes in Obsidian's reading view. They're great for making key information pop without interrupting the flow of your narrative.

---

## 5. Block IDs (`^block-id`) - Bookmark Any Paragraph

This is incredibly handy for session notes. Add a `^block-id` on a blank line after any paragraph to create a "bookmark" you can link to from anywhere.

**Step 1:** Tag the paragraph where something happens:
```markdown
Zalros drew the constellation on the glass case using his Illuminator's
Tattoo, and the glass case opened. ^longsword-found
```

**Step 2:** Link to it from your loot section, another session, or anywhere:
```markdown
- **Longsword +3** - Three gem slots, requires attunement.
  ([[#^longsword-found|Where we found it]])
```

The `#` means "this file" - for cross-file links, use the full filename:
```markdown
([[Session 2 - Mutual Ache for Something More#^longsword-found|Where we found it]])
```

**Naming tips:**
- Keep IDs short but descriptive: `^longsword-found`, `^chisum-met`, `^coffin-cliffhanger`
- Use lowercase with hyphens (no spaces)
- The block ID line must be on its own line with a blank line before it

You can also build a **Locations Visited** list using block IDs to show every time a place comes up:

```markdown
- **Samwell's Storage Room** - [[#^storage-room-figurines|Figurines]] / [[#^storage-room-teleportation-circle|Teleportation circle]]
- **Gosslupe Market** - [[#^gobblin-it-up|Gobblin' it Up]] / [[#^pig-purchased|Brog's pig]] / [[#^mystery-scrolls-purchased|Scrolls]]
```

> **Pro tip:** Avoid using aliased links (`[[link|text]]`) inside markdown tables - the `|` in the link conflicts with the table's cell separators and Obsidian's linter will break them. Lists work great for this instead!

Check out the **Session 2 - Example With Obsidian Features** file in this branch to see all of this wired up and working!

---

## 6. Embedded Links and Images (`![[]]`)

You've got character photos in your `Character Photos/` folder already. You can embed them directly in your notes!

```markdown
### Chisum
![[Chisum.png|200]]

A charming young curiosities vendor who took quite the interest in
[[Zalros]], though Zalros remained cheerfully oblivious.
```

The `|200` controls the width in pixels. This works for images and for embedding entire pages - so if you made a `Chisum.md` page, you could embed it inside a session note with `![[Chisum]]`.

---

## 7. Putting It All Together - A Real Example

Here's what a paragraph from your Session 2 notes could look like using all of these features:

```markdown
[[Elara]] visited a general store stall and purchased a bundle of arrows
as well as some "mystery scrolls" - their effects were unknown, but because
of that, they were being sold for cheap. Elara grabbed a purple and green
scroll. Elara then made her way to the adventurer's guild, encountering a
group of young and brash adventurers who quickly received a scolding from
[[Jarvis]], an experienced adventurer who gave his [[Jarvis' Calling Stone|calling stone]]
to Elara and promised to find some information on [[Asta Vale]], Elara's sister.

> [!tip] Loot Acquired
> **Mystery Scrolls (Purple & Green)** - Unknown effects. Purchased cheap.
> **Jarvis' Calling Stone** - Given by [[Jarvis]]; will relay info about [[Asta Vale]].
```

Notice how the narrative stays clean and readable, the links create a web of connections, and the callout box clearly separates the "game info" from the "story."

---

## 8. Recommended Vault Structure

As your campaign grows, consider organizing like this:

```
Teldire Campaign/
  Sessions/
    Session 1 - Of Marrow & Maple.md
    Session 2 - Mutual Ache for Something More.md
    Session 3 - ...
  Characters/
    PCs/
      Zalros.md
      Elara.md
      Brog.md
      Shamash.md
      Drakka.md
    NPCs/
      Samwell.md
      Jarvis.md
      Chisum.md
      Rosetta.md
  Locations/
    Gosslupe.md
    Samwell's Tower.md
    The Kiln.md
  Lore/
    Teldire Bible.md
    Zalros - Full Deep Dive.md
    The Jeering Sparrow.md
    Skeleton Crew.md
  Items/
    Longsword +3.md
    Gem of Brightness.md
  Character Photos/
    (your existing images)
```

You don't need to set all of this up at once. The beauty of Obsidian is that you can just start linking things with `[[]]` in your session notes, and then create the pages later when you feel like fleshing them out. Empty links are totally fine - they're just reminders that "this thing exists and might deserve its own page someday."

---

## Quick Reference Cheat Sheet

| Feature | Syntax | What it does |
|---|---|---|
| Internal link | `[[Page Name]]` | Clickable link to another page |
| Aliased link | `[[Page Name\|Display Text]]` | Link that shows different text |
| Tag | `#tag-name` | Searchable label |
| Embed image | `![[image.png\|width]]` | Shows an image inline |
| Embed page | `![[Page Name]]` | Embeds another page's content |
| Callout | `> [!type] Title` | Colored info box (tip, warning, info, etc.) |
| Frontmatter | `---` block at top | Metadata (tags, date, session number) |
| Block ID | `^my-block-id` | Bookmark a paragraph for linking |
| Block link | `[[#^block-id\|text]]` | Jump to a bookmarked paragraph |
| Checkbox | `- [ ] Task here` | Interactive checklist item |

Happy note-taking! Your session notes are already really solid narratively - these tools will just help you connect the dots across sessions as the campaign grows.
