# Do Think Twice 三思而后行

An agent skill for Codex and Claude that checks whether a suggested change is actually worth making before giving advice, edits, rewrites, or refactors.

## Why

AI assistants often suggest changes because they can, not because the change is clearly better than the original.

**Do Think Twice** adds a simple discipline: before recommending a change, compare the proposed change against keeping the original. Different is not automatically better. A recommendation should only appear when its expected benefit is greater than its cost, risk, and uncertainty.

三思而后行：先判断改动是否真的值得，再给建议。

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
npx skills add eClip8e-coder/do-think-twice -a codex -g -y
```

If your installer asks for a specific skill name, use:

```bash
npx skills add eClip8e-coder/do-think-twice --skill do-think-twice -a codex -g -y
```

After installation, invoke it by name:

```text
Use do-think-twice to review this paragraph.
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
npx skills add eClip8e-coder/do-think-twice -a claude-code -g -y
```

If your installer asks for a specific skill name, use:

```bash
npx skills add eClip8e-coder/do-think-twice --skill do-think-twice -a claude-code -g -y
```

After installation, invoke it by name:

```text
Use do-think-twice to review this diff.
```

Depending on your Claude Code skill setup, it may also be available as:

```text
/do-think-twice
```

## Manual Install

If you do not use the skills installer, copy the skill folder into your agent skills directory:

```text
skills/do-think-twice
```

For example, on Windows with Codex:

```powershell
git clone https://github.com/eClip8e-coder/do-think-twice.git
Copy-Item -Recurse .\do-think-twice\skills\do-think-twice "$env:USERPROFILE\.codex\skills\do-think-twice"
```

On macOS or Linux with Codex:

```bash
git clone https://github.com/eClip8e-coder/do-think-twice.git
mkdir -p ~/.codex/skills
cp -R do-think-twice/skills/do-think-twice ~/.codex/skills/do-think-twice
```

## Update

If installed with the skills installer:

```bash
npx skills update -g -y
```

If installed manually, pull the repository and copy `skills/do-think-twice` again.

## Project Layout

```text
do-think-twice/
├── README.md
├── LICENSE
├── package.json
└── skills/
    └── do-think-twice/
        ├── SKILL.md
        └── agents/
            └── openai.yaml
```

The skill is intentionally instruction-only. It has no scripts, assets, build step, or runtime dependencies.

## Skill Contents

The actual agent instructions live here:

```text
skills/do-think-twice/SKILL.md
```

The UI metadata for compatible agents lives here:

```text
skills/do-think-twice/agents/openai.yaml
```

## Uninstall

If installed with the skills installer:

```bash
npx skills remove eClip8e-coder/do-think-twice -g
```

If installed manually for Codex, delete:

```text
~/.codex/skills/do-think-twice
```

## License

MIT License.
