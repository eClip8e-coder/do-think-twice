# reflective-check

A Codex skill that evaluates whether a suggested change is truly worth making before giving advice or editing.

## What it does

`reflective-check` makes Codex compare a proposed change against keeping the original before recommending edits, rewrites, refactors, design changes, wording changes, formatting changes, or strategy shifts.

The core rule is simple: different is not automatically better. A recommendation should only be given when its expected benefit is greater than its cost, risk, and uncertainty.

## When to use it

Use this skill when reviewing or improving:

- advice and critique
- writing, polishing, and editing
- academic papers, abstracts, figures, citations, and revision plans
- resumes and professional text
- code reviews and refactors
- image, SVG, and layout edits
- optimization or strategy comparisons

It is also intended for prompts such as:

- "What should I change?"
- "Is this better?"
- "还有什么可以改?"
- "检查一下还有哪些问题?"

## How it responds

The skill filters suggestions by value instead of listing every possible change.

Recommendations are classified as:

- **Must fix**: real errors, rule violations, misleading meaning, or blockers.
- **Strongly recommended**: clear improvement with low risk.
- **Optional**: minor improvement where the original is also acceptable.
- **Not recommended**: unnecessary, risky, or merely a style preference.

When the original is already good, the skill says so directly. When no change is needed, it recommends keeping the original.

## Skill location

```text
.agents/skills/reflective-check/SKILL.md
```

This is an instruction-only Codex skill. It does not include scripts, assets, or extra runtime dependencies.
