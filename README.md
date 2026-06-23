# Agentic Second Brain

Claude starts every session not knowing who you are, how you work, or where things live. Agentic Second Brain fixes that: a plain-text folder it reads at startup, so it stops guessing.

Unlike a classic second brain, you barely read this one. Your assistant works from it: your context, projects, skills, and routines as plain files, so the agent knows what to load and when.

You install one coach, and it builds the rest with you, one step at a time. Works with **Cowork** and **Claude Code**; **Codex** and other agents use the same folder through `AGENTS.md`.

> **Language.** The coach speaks Rioplatense Spanish (that is the method's personality), and the starter folders use Spanish names you can rename. Your own brain and content stay in whatever language you work in. Spanish README: [README.es.md](README.es.md).

---

## The difference shows up in session two

You feel it the second time you open Claude: you do not explain the same context again.

```text
Session 1, no brain:
  You: I'm a freelance designer, my stack is X, I'm on the Acme rebrand,
       keep the tone casual... (every session, from scratch)

Session 2, with the brain:
  You:    draft the Acme update email
  Claude: (already knows who you are, the project, your tone) Here's a draft...
```

That gap is the whole point.

## The toolkit, ready on day one

You do not have to build these. The plugin ships slash commands that work the moment you install it, before you set anything up:

| Command | What it does |
|---|---|
| `/asb` | Front desk: lists your tools and points you to the coach |
| `/asb-slop` | Strips the AI smell from a text in one pass |
| `/asb-write` | Writes or rewrites in your voice |
| `/asb-prompt` | Turns a rough ask into a paste-ready prompt for any AI chat |
| `/asb-panel` | 2 to 5 reviewers, different lenses, on something before you send it |
| `/asb-council` | A council of 5 advisors for a decision with real stakes |
| `/asb-deck` | Builds a presentation in stages, rough to final |
| `/asb-audit` | Health check of your second brain |
| `/asb-doc` | Closes a session: routes everything durable to its place |
| `/asb-simple` | Lost the thread? Plain-language recap: where we are, your move, mine |

These are stock tools that work the same for everyone. The coach (`/asb-coach`) builds the part that is yours: your projects, identity, and your own skills. (A *skill* is a saved recipe a phrase triggers. Using these is the fastest way to see what one is before you write your own.)

They run as slash commands in both Cowork and Claude Code, with no setup. In Cowork you can also trigger them by describing what you want.

## Install

### Cowork (no terminal)

1. In the **Customize** panel, under **Personal plugins**, click **+** and choose **Create plugin -> Add marketplace**. Paste: `brunogiel/agentic-second-brain`
   (shortcut if you can type: `/plugin marketplace add brunogiel/agentic-second-brain`).
2. Install the **agentic-second-brain** plugin
   (or type `/plugin install agentic-second-brain@agentic-second-brain`).
3. Open or create the folder where your brain should live. A synced folder is best: Drive, iCloud, or Dropbox.
4. Use one of:
   - `/asb` (start here): the front desk, with your toolkit and where you stand
   - `/asb-coach`: the coach that sets up your system, locates you, and proposes the next step

The coach asks before creating files. It does not build folders behind your back. In Cowork, the plugin updates itself.

### Claude Code

```bash
curl -fsSL https://raw.githubusercontent.com/brunogiel/agentic-second-brain/main/install.sh | bash
```

It installs the method and commands globally and does not touch your brain folder. Then open the folder where you want to work and type:

```text
/asb        # front desk: your toolkit + where you stand (start here)
/asb-coach  # the coach: sets up your system, locates you, proposes next step
```

## What this is not

- **Not a notebook you read.** Unlike Obsidian or Notion, you are not the reader. Your assistant is.
- **Not a dev framework.** Methods like BMAD run a software build; this holds your whole working context. They coexist.
- **Not raw Claude.** You stop re-introducing yourself and your projects every session.

## How it works

The model writes text. The client (Cowork, Claude Code, Codex) gives it hands to read and edit files. Your folder gives it the context: who you are, what projects exist, what rules to follow, and where to look. Three plain ingredients, no magic.

## What gets installed

Two parts, kept separate:

- **The method** lives outside your folder. In Cowork it is a plugin; in Claude Code it lives in `~/.claude/skills/`. The coach, templates, and kit catalog live here.
- **Your brain** lives in your synced folder, and holds only your stuff.

Your brain folder ends up looking like this:

```text
CLAUDE.md        # the router your assistant reads first
ESTADO.md        # short status, to resume fast
ESCALERA.md      # your progress + the kit catalog
AGENTS.md        # pointer for non-Claude agents
0. Inbox/        # capture without deciding
1. Proyectos/    # projects, one folder each
2. Áreas/yo/     # who you are, how you work, your voice
3. Recursos/     # reusable references
4. Archivo/      # done or dormant
skills/          # the skills you have activated
```

The `kit/` directory in this repo belongs to the method, not your brain: `kit/brain/` holds the folder templates, `kit/skills/` holds the catalog the coach activates one at a time.

## Already have a system?

You do not have to migrate. The coach reads your structure and keeps it.

The rule is simple: there must be a clear router (`CLAUDE.md` or `AGENTS.md`) that says where things live. If your structure already works, the coach does not rename it or force PARA. It only proposes small improvements: inbox, shortcuts, decision logs, skills, or session state.

## What it touches

- The Claude Code installer only installs the global method.
- The coach creates files in your brain only after you approve.
- Existing files are not overwritten.
- Updates refresh the method, not your folder.
- Uninstall removes the engine, not your data.

To uninstall in Claude Code:

```bash
curl -fsSL https://raw.githubusercontent.com/brunogiel/agentic-second-brain/main/uninstall.sh | SB_YES=1 bash
```

In Cowork, uninstall the plugin from the UI or type `/plugin uninstall agentic-second-brain`.

## The ladder

You do not build everything on day one. You climb one step at a time.

| Level | What you build | What it gives you |
|---|---|---|
| **0** | Identity + inbox | The assistant knows who you are and loose ideas are not lost |
| **1** | First project with `CLAUDE.md` | You stop re-explaining context and decisions |
| **2** | Phrase -> folder shortcuts | Say "my expenses" and it knows where to look |
| **3** | First custom skill | One phrase triggers a repeated recipe |
| **4** | Routine + connected tool | The system can read mail, calendar, or tasks |
| **5** | Orchestrator | Several skills work together on one task |
| **6** | Audit and tuning | You keep the system from degrading |
| **If you code** | Code separated from context | The repo keeps code; the brain keeps decisions |

The coach reads `ESTADO.md` and `ESCALERA.md`, tells you where you are, and proposes one next step.

## Portability

Your brain is plain text. You can open the same folder in Cowork, Claude Code, Codex, or Cursor.

Use-skills live in `skills/` and are activated through the **Mis skills** table in `CLAUDE.md`. Codex and Cursor reach that table through `AGENTS.md`. The only Claude-specific piece is the setup engine: `/asb-coach` and, in Claude Code, `actualizar`. If you use another agent, `AGENTS.md` includes a fallback workflow.

## Skills

Most kit skills are the toolkit above, available as `/asb-*` commands from day one. The coach can also activate any of them as an editable skill in your own `skills/` folder as you climb. Three more have no command, and the coach adds them when you reach their level: `crear-skill` (build your own), `triage` (a daily brief from connected mail, calendar, and tasks), and `evaluar-skill` (grade a skill against its rubric).

## Philosophy

- Propose, you decide.
- One step at a time.
- Small files, read only when needed.
- Skills stay dormant until a phrase activates them.
- Your folder stays clean: only your stuff.

## Credit

Made by [Bruno Gielczynsky](https://www.linkedin.com/in/brunogiel/). Part of a family of installable AI methods alongside [Empat.ia](https://github.com/brunogiel/Empat.ia).

## License

MIT. Use it, fork it, make it yours.
