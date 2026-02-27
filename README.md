---
tags:
  - ai_generated
---

# My Obsidian Vault Setup: A Walk-Through for the Curious

You just installed Obsidian. You open it up, create a new vault, and there it is an empty folder. A blinking cursor. No structure, no rules, no guardrails. Just you and a blank canvas.

That feeling is both freeing and terrifying.

This is the story of how my vault grew from that blank canvas into a system I actually use every single day. If you're just getting started with Obsidian, maybe this gives you some ideas. If you're a fellow vault-tinkerer, maybe you'll spot something worth stealing.

## The skeleton: PARA with a twist

Early on I knew I needed some kind of folder structure, or I'd end up with 300 notes in a single pile. I landed on **PARA**, Tiago Forte's system of organizing things into **Projects, Areas, Resources, and Archive**. It clicked because it maps to how I actually think about work: some things are active initiatives with a deadline, some are long-running responsibilities, some are just reference material I might need someday, and some are done and should get out of my way.

My vault looks like this:

```
00_CAPTURE/         ← the inbox (more on this in a moment)
01_KNOWLEDGE/
  00_PROJECTS/      ← active initiatives with clear outcomes
  01_AREAS/         ← ongoing domains I'm responsible for
  02_RESOURCES/     ← documentation, partner specs, schemas
  03_ARCHIVE/       ← done and dusted
99_SYSTEM/          ← templates and automation scripts
```

The numbered prefixes are purely cosmetic, they keep the folders in a predictable order in the file explorer. `00_CAPTURE` always sits at the top because that's where everything starts.

## The linking philosophy: borrowing from Zettelkasten

I don't run a strict Zettelkasten. I don't assign unique numeric IDs to every note or maintain a rigid index. But I borrowed its most powerful idea: **link everything**.

Every note in my vault is connected to other notes through Obsidian native `[[wikilinks]]`. A meeting note links to the project it belongs to. A decision links back to the business case that prompted it. A daily note links to the standup summary and the three calls I had that day.

Over time, these links form something beautiful. Open the graph view and you can literally see clusters of related thinking. Backlinks surface connections you forgot you made. The vault starts thinking *with* you, not just storing things *for* you.

That's the Zettelkasten spirit - atomic notes, densely connected, even if I don't follow the method by the book.

## The daily note: where everything begins

If there's one thing that makes this whole system work, it's the daily note.

Every morning, I hit the today date on a calendar and Obsidian creates a fresh note from a template, drops it into `00_CAPTURE/`, and I'm off. That note becomes the central hub for the entire day. And I mean *everything* goes into it.

Had a meeting? I don't open a separate file. I just drop a heading right inside the daily note, something like `# 2026-02-27 Sprint Planning`, and write my bullet-point notes below it. A random idea pops up between calls? I jot it down inline, no heading needed. A task I need to remember? Same thing, just type it wherever I am in the note. The daily note is one continuous stream of everything that happened that day.

The processing happens later, usually at the end of the day, or sometimes I let it pile up and do a batch at the end of the week. I extract a meeting section into its own note, Obsidian's note composer makes this a one-click operation, and it automatically leaves a `[[link]]` behind in the daily note pointing to the new file. So the daily note transforms from a dense capture log into a clean index of the day, with links to all the meetings and notes that were born from it.

Random thoughts and tasks that I wrote inline between the headings? They stay right where they are. They don't need their own file. They're small, they're contextual, and the task plugin picks them up anyway.

That's why the daily note works as my inbox, scratchpad, and launchpad, all in one file. During the day I never think about *where* something goes. It all goes here. Structure comes later, when I process the daily note and push extracts to the right location outside of `00_CAPTURE/`: meeting notes and the daily note itself go into `03_ARCHIVE`, persistent knowledge lands in `01_AREAS`, project artifacts and deliverables go into `00_PROJECTS`, and new reference links or documents end up in `02_RESOURCES`.

This capture-then-process rhythm is the heartbeat of the vault. `00_CAPTURE/` is always a little messy, and that's fine, it's supposed to be. The knowledge base in `01_KNOWLEDGE/` stays clean because nothing lands there unprocessed.

## Simple Tasks: the plugin I built because nothing else fit

I tried several task management plugins. They were either too complex, too opinionated, or they stored data in their own databases which made me nervous about portability. So I built my own. You can find it on GitHub: [Simple Tasks](https://github.com/gogothegogo/Simple-tasks).

**Simple Tasks** is a stateless, zero-database task plugin. Tasks are just regular markdown checkboxes with one addition, categories using Obsidian's highlight syntax:

```markdown
- [ ] ==TODO== Review the pricing proposal
- [ ] ==DECISION== Approve the new terminal supplier
- [ ] ==IDEA== Explore OCPP protocol for EV charging
```

That's it. No proprietary format, no sidecar files, no database. If you open the file in any text editor, you can still read and edit your tasks.

What the plugin adds is *aggregation*. I drop a `simpletasks` code block into my daily note template, configure it to show undone tasks from a certain category, and it scans the entire vault in real-time to build the list. My daily note template comes with three views baked in: **ToDo**, **Decisions**, and **Ideas**. Each morning I see exactly what's on my plate, pulled live from every corner of the vault.

Typing `[]` anywhere triggers an autocomplete that lets me pick a category and formats the line as a task. Categories show up as clickable chips in the task views. I can filter by folder, by tag, by date range, all interactively, and I can save those filter settings back into the code block with a single click.

The beauty of this approach is that tasks live *where they belong*. A task born in a meeting note stays in that meeting note. A task I jot down in my daily note stays there. Simple Tasks just gives me a lens to see them all at once without moving them anywhere.

## The daily flow

A typical day looks like this:

1. Open the daily note. Scan the three task views, what's pending, what decisions are waiting, what ideas are floating around.
2. Throughout the day, capture everything in the daily note or in linked meeting notes. Create tasks inline with `[]` autocomplete.
3. At the end of the day (or when I have a quiet moment), process the captures. Move polished notes into the right location outside of `00_CAPTURE/`. Link things together. Archive what's done.
4. Repeat.

Over weeks and months, `01_KNOWLEDGE/` grows into a proper knowledge base, interconnected, searchable, and genuinely useful. Projects fill up with roadmaps and deliverables, areas accumulate domain expertise, resources collect the documentation and references I keep coming back to, and the archive becomes a detailed log of daily notes, finished projects, and everything that's run its course.

## The takeaway

My vault isn't perfect. It's not supposed to be. It's a living system that evolved through daily use, not through upfront design. The combination of PARA for structure, Zettelkasten-style linking for connections, daily notes as the entry point, and a simple homegrown task plugin for execution, that's what works for me.

The best productivity system is the one you actually use. Mine just happens to live in a folder full of markdown files.
