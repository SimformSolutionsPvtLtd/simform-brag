# Using /simform-brag with other AI coding agents

Agents like **Cursor**, **Aider**, or any LLM with custom instructions don't have native `SKILL.md` discovery. Use one of these methods:

## Option 1: Paste into custom instructions

Open your agent's custom instructions or system prompt settings and paste the full contents of [`skills/simform-brag/SKILL.md`](../skills/simform-brag/SKILL.md).

## Option 2: Reference as a file path

If your agent supports loading instructions from a file, point it at:

```
path/to/skills/simform-brag/SKILL.md
```

## Option 3: Copy the skill folder

Copy `skills/simform-brag/` into wherever your agent looks for skill files:

```bash
cp -r skills/simform-brag/ ~/.your-agent/skills/simform-brag/
```

## Prerequisites

Regardless of method, the environment needs:
- **Node.js 22+**
- **FFmpeg** on `PATH`
- **Hyperframes CLI** — `npx hyperframes doctor` to verify
- **This repo cloned** (or `skills/simform-brag/` accessible) for assets (music, SFX, reference docs)
