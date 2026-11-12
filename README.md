# persona-replica

Turn a real person's photos, videos, and speaking habits into a consistent AI persona, one whose chats, selfies, videos, and proactive messages stay recognizably *that person*.

一个把真人的照片、影片与说话习惯，做成「像本人」的 AI 分身的方法项目：聊天、自拍、影片和主动讯息都保持一致的长相、语气与生活节奏。

## Overview

Most AI personas drift. The face changes between generations, the voice slips back into assistant-speak, and the character forgets what it said an hour ago. `persona-replica` is a field-tested method that prevents that drift. It treats likeness as an engineering problem with three parts:

1. **Identity** — a written feature spec and exclusion list extracted from reference material, locked as the single standard for every generation.
2. **Behavior** — a speaking-style engine built on short segmented messages, emotion-first replies, and deliberate variability.
3. **Presence** — a modeled daily life (schedule, places, states) plus scheduled, conditional proactive messages, so the persona lives on its own clock instead of only answering.

## Features

- **Material intake checklist** — exactly which photos, videos, speaking samples, and life facts to collect, and what to mark as never-to-fabricate.
- **Feature spec + exclusion list** — a durable standard for face, hair, skin, signature items, and body proportions.
- **Two-step video workflow** — verify a still photo against the spec first, then animate it. This measurably reduces face drift compared with generating video directly from references.
- **Life modeling** — schedule, environments, and state mapping (tired after X, free at Y), verified sources separated from modeled estimates.
- **Speaking-style rules** — short bubbles, emotion first, full emotion range, no repeated templates, in-character deflections for unknown facts.
- **Proactive messaging** — scheduled touches tied to real daily events, each with a silence condition and a hardship rule.
- **Correction discipline** — every user correction becomes a dated hard rule; the newest correction always wins.

## Quick start

1. Copy `templates/PERSONA.template.md` to your working folder and rename it for your subject, e.g. `personas/<name>/PERSONA.md`.
2. Work through `docs/intake-checklist.md` and collect the source material into `personas/<name>/references/`.
3. Fill in the feature spec and exclusion list from the references.
4. Give your AI agent the `SKILL.md` in this repo and ask it to build the persona. From then on, every generation and message follows the standard in `PERSONA.md`.

## Repository structure

```
persona-replica/
├── SKILL.md                  # The method, written for an AI agent to follow
├── skill.yaml                # Skill descriptor (name, title, description)
├── docs/
│   ├── intake-checklist.md   # Source material to collect, with acceptance criteria
│   ├── likeness-workflow.md  # Photo and video generation workflow in detail
│   ├── speaking-style.md     # Chat behavior rules
│   └── proactive-messaging.md# Scheduled contact patterns and silence conditions
├── templates/
│   └── PERSONA.template.md   # Fill-in standard for one persona
├── examples/
│   └── example-persona.md    # A fully fictional worked example
├── CHANGELOG.md
├── CONTRIBUTING.md
└── LICENSE
```

## Documentation

- [Intake checklist](docs/intake-checklist.md) — what to collect and how to judge whether a reference is usable.
- [Likeness workflow](docs/likeness-workflow.md) — reference selection, the two-step video workflow, and the pre-delivery checklist.
- [Speaking style](docs/speaking-style.md) — how the persona texts, and the failure modes to check before sending.
- [Proactive messaging](docs/proactive-messaging.md) — turning a routine into scheduled, conditional contact.

## Status

v0.1.0 — initial public structure. The method is in daily use; the docs are being expanded from project notes.

## Contributing

Corrections, better workflows, and additional worked examples are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

MIT — see [LICENSE](LICENSE).
