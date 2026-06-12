# reflective-check

An agent skill for Codex and Claude Code that checks whether a suggested change is actually worth making before giving advice, edits, rewrites, or refactors.

## Why

AI assistants often suggest changes because they can, not because the change is clearly better than the original.

`reflective-check` adds a simple discipline: before recommending a change, compare the proposed change against keeping the original. Different is not automatically better. A recommendation should only appear when its expected benefit is greater than its cost, risk, and uncertainty.

## What It Does

This skill helps AI coding agents avoid over-suggesting during:

- critique and review
- rewriting, polishing, and editing
- academic paper revision
- resume revision
- code review and refactoring
- image, SVG, and layout editing
- optimization and strategy comparison

It classifies recommendations as:

| Category | Meaning |
| --- | --- |
| Must fix | A real error, rule violation, misleading meaning, or blocker. |
| Strongly recommended | Clear improvement with low risk. |
| Optional | Minor improvement; the original is also acceptable. |
| Not recommended | Unnecessary, risky, or only a style preference. |

When the original is already good, the skill tells the user to keep it.

## Install

Most users should install the skill globally so it is available in every project.

### Codex

```bash
npx skills add eClip8e-coder/reflective-check -a codex -g -y
```

If your installer asks for a specific skill name, use:

```bash
npx skills add eClip8e-coder/reflective-check --skill reflective-check -a codex -g -y
```

After installation, invoke it by name:

```text
Use reflective-check to review this paragraph.
```

You can also ask Codex naturally:

```text
What should I change?
Is this better?
还有什么可以改?
检查一下还有哪些问题?
```

### Claude Code

Claude Code users can install the same skill globally:

```bash
npx skills add eClip8e-coder/reflective-check -a claude-code -g -y
```

If your installer asks for a specific skill name, use:

```bash
npx skills add eClip8e-coder/reflective-check --skill reflective-check -a claude-code -g -y
```

After installation, invoke it by name:

```text
Use reflective-check to review this diff.
```

Depending on your Claude Code skill setup, it may also be available as:

```text
/reflective-check
```

## Manual Install

If you do not use the skills installer, copy the skill folder into your Codex skills directory:

```text
skills/reflective-check
```

For example, on Windows:

```powershell
git clone https://github.com/eClip8e-coder/reflective-check.git
Copy-Item -Recurse .\reflective-check\skills\reflective-check "$env:USERPROFILE\.codex\skills\reflective-check"
```

On macOS or Linux:

```bash
git clone https://github.com/eClip8e-coder/reflective-check.git
mkdir -p ~/.codex/skills
cp -R reflective-check/skills/reflective-check ~/.codex/skills/reflective-check
```

## Update

If installed with the skills installer:

```bash
npx skills update -g -y
```

If installed manually, pull the repository and copy `skills/reflective-check` again.

## Project Layout

```text
reflective-check/
├── README.md
├── LICENSE
├── package.json
└── skills/
    └── reflective-check/
        ├── SKILL.md
        └── agents/
            └── openai.yaml
```

The skill is intentionally instruction-only. It has no scripts, assets, build step, or runtime dependencies.

## Skill Contents

The actual Codex instructions live here:

```text
skills/reflective-check/SKILL.md
```

The UI metadata for compatible agents lives here:

```text
skills/reflective-check/agents/openai.yaml
```

## Uninstall

If installed with the skills installer:

```bash
npx skills remove eClip8e-coder/reflective-check -g
```

If installed manually, delete:

```text
~/.codex/skills/reflective-check
```

## License

MIT License.
