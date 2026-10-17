---
name: video-location-app-planner
description: Plans a video app that shows where each video was recorded, producing a feature table, screen list, simple data model, and privacy and permissions checklist as a short Markdown plan. Use when the user says plan a video app with location, add a map to my video app, or show where my videos were recorded. Aimed at beginner and intermediate app developers and students building a mobile or web video app with a map. Not for writing the full app code, collecting or storing location without clear user consent, tracking people in real time, or giving legal advice about privacy laws.
license: MIT
---

# Video Location App Planner

Plan a video app that shows where each video was recorded. Output is a short
Markdown plan, never full app code.

## When to use this skill

Use when the user says things like:

- "plan a video app with location"
- "add a map to my video app"
- "show where my videos were recorded"
- or asks for a feature list, screen list, data model, or permission
  checklist for a video app with a map

Do not use when the user wants working app code, real-time tracking of people,
or legal advice.

## Gather from the user first

Ask only about items the user has not already answered:

1. **Platform** - iOS, Android, web, or cross-platform (for example React
   Native or Flutter)?
2. **Target users** - consumers, students, an internal team, or other?
3. **Location source** - does the location come from video metadata (GPS the
   device writes while recording), from the user entering it or dropping a
   pin, or both?
4. **Map scope** - one shared map of all videos, a personal library map, or
   other?

If the user does not know, assume a simple consumer app where location comes
from video metadata with manual entry as a fallback, and state the assumption
in the plan.

## Step-by-step process

1. Confirm platform, target users, and location source (skip answers already given).
2. Draft the feature table: features with a one-line description and a
   priority of Must, Should, or Could.
3. Draft the screen list: each screen by name plus what it shows and what the
   user can do there.
4. Draft the data model: the entities and fields listed under Output format.
5. Read [references/privacy-permissions-checklist.md](references/privacy-permissions-checklist.md)
   and fill in every checklist item as Yes, No, or TODO for this app.
6. Mark any platform fact you are not fully sure of (exact permission names,
   map SDK limits, store review rules) with VERIFY in the plan instead of
   stating it as fact.
7. Assemble the four sections in the output format and present them as one
   short Markdown plan.

## Output format

One short Markdown document with exactly these four sections:

```markdown
## Feature table
| Feature | Description | Priority |
|---|---|---|
| Video grid | Browse recorded videos | Must |
| Location map | Show a pin for each video's location | Must |

## Screen list
1. Video grid - lists videos with thumbnails; tap opens the player
2. Video player - plays one video and shows its recorded location
3. Map view - one pin per video; tap a pin opens that video
4. Add or edit location - user confirms or fixes a video's location

## Data model
- **Video** - id, title, file reference, recorded_at, thumbnail
- **Location** - id, video_id, latitude, longitude, source (metadata or
  user-entered), consent_given, created_at
- **User** - id, consent_status (only if accounts exist)

## Privacy and permissions checklist
- [ ] Location source is declared (metadata / user-entered / both) - Yes
- [ ] Permission prompt explains why location is needed - TODO
- ... (one line per item from the reference, each marked Yes, No, or TODO)
```

Keep the whole plan short enough for a beginner to read in a few minutes.

## What not to do

- Do not write the full app code. Plan only; a few field names or tiny
  pseudocode snippets in the data model are the limit.
- Do not collect or store location without clear user consent. Consent must
  appear in the plan as an explicit step before any location is saved.
- Do not plan real-time tracking of people or devices. Locations attach to
  recorded videos only.
- Do not give legal advice about privacy laws. The checklist states what to
  ask a lawyer, never what the law requires.
- Do not invent facts. Exact platform permission names, map SDK limits, and
  store rules change; mark them VERIFY and let the user confirm them against
  official documentation.
