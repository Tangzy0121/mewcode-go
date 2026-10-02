# mewcode-go

A terminal AI coding agent built from scratch in Go — agent loop, tool calling, permission gating, streaming TUI.

一个用 Go 从零实现的终端 AI 编码智能体（v1.0 建设中）。

## Status

v1.0 in progress: working through a course chapter by chapter, each chapter landing with **real-machine evidence** (a reproducible command and its actual output using a real model key) and a short divergence note. Nothing is marked done on unit tests alone.

## How this is built

The code is implemented by AI; the architecture decisions and the review are mine. Every chapter must leave three kinds of audit evidence — explain (describe the chapter's data flow without looking at the code), change (hand-modify a requirement and predict the result first), catch (record one AI mistake or rejected approach). See [ADR-0002](./docs/adr/0002-ai-implements-human-architects.md).

## Map

- `GLOSSARY.md` — project vocabulary (Chinese)
- `docs/roadmap.md` — chapter-by-chapter plan and milestones
- `docs/adr/` — decisions worth remembering
- `docs/review/<chapter>.md` — audit evidence per chapter
- `docs/notes/<chapter>.md` — my own study notes (never course material)
- v0, kept for comparison only: [Tangzy0121/mewcode-v0](https://github.com/Tangzy0121/mewcode-v0) — a complete-looking skeleton that was never verified against a real model. See [ADR-0001](./docs/adr/0001-restart-as-mewcode-go.md).

## Contributing

Solo learning project — issues and notes are welcome, pull requests are not expected.
