# video-location-app-planner

An Agent Skill that follows the open Agent Skills specification
(agentskills.io/specification). It helps an AI agent plan a video app that
shows where each video was recorded. The agent produces a short Markdown
plan containing a feature table, a screen list, a simple data model for
videos and locations, and a privacy and permissions checklist - not app code.

**For:** beginner and intermediate app developers and students building a
mobile or web video app with a map.

**Trigger phrases:** "plan a video app with location", "add a map to my
video app", "show where my videos were recorded".

**Not for:** writing the full app code, collecting or storing location
without clear user consent, real-time people tracking, or legal advice
about privacy laws.

## Folder structure

```
video-location-app-planner/
├── SKILL.md                                  # Required. Frontmatter + instructions the agent follows
├── references/
│   └── privacy-permissions-checklist.md      # Detailed checklist the agent fills in per plan
├── README.md                                 # This file
└── LICENSE                                   # MIT, 2026
```

## What each file does

- **SKILL.md** - the skill itself. Its YAML frontmatter (name, description,
  license) lets an agent discover and activate the skill; the body tells the
  agent when to use it, what to ask the user first, the step-by-step
  process, the exact output format, and the rules on what not to do.
- **references/privacy-permissions-checklist.md** - the long reference
  material. The agent reads it only while step 5 of the process is running,
  which keeps SKILL.md short.
- **README.md** - this file, for humans who want to install or audit the
  skill.
- **LICENSE** - the MIT license text.

## How to install

Copy the whole `video-location-app-planner/` folder into the skills
directory your agent reads. That location depends on the agent, so check
your agent's documentation - for example some agent setups load skills from
`~/.claude/skills/` or `~/.agents/skills/`. The folder name must stay
`video-location-app-planner` because the skill's `name` field must match it.

## How to validate

From the parent folder of the skill:

```bash
pip install skills-ref
skills-ref validate ./video-location-app-planner
```

If you do not have pip, try `python3 -m pip install skills-ref`. The
validator checks the frontmatter and naming rules (lowercase letters,
numbers, hyphens; no leading/trailing/double hyphens; `name` matches the
folder; description under 1024 characters).

## Facts this skill deliberately does not assert

To avoid inventing facts, the skill marks these for verification against
current official sources instead of stating them as truth:

- Exact Android runtime permission names and when each is required
- Exact iOS Info.plist location usage-description keys
- Browser geolocation secure-context rules
- App Store / Google Play privacy form requirements and map SDK quotas
- Obligations under any privacy law (the skill gives no legal advice; it
  lists questions for a lawyer instead)
