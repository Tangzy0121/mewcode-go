# mewcode-go — Repository Conventions

Go implementation of a terminal AI coding agent, built by working through a course chapter by chapter. Repo: `Tangzy0121/mewcode-go`.

## Agent skills

### Issue tracker

Issues and specs live as GitHub issues (repo `Tangzy0121/mewcode-go`), via the `gh` CLI. See `docs/agents/issue-tracker.md`.

### Triage labels

The five canonical roles keep their default names. See `docs/agents/triage-labels.md`.

### Domain docs

Single-context: `GLOSSARY.md` + `docs/adr/` at the repo root. See `docs/agents/domain.md`.

## How this repo is built

- **Code is implemented by AI; architecture decisions and review are human.** See `docs/adr/0002-ai-implements-human-architects.md`.
- **Every chapter/ticket must land evidence, not just code**: one real-machine evidence item (a reproducible command plus its actual output from a real model key — unit tests passing does not count), one divergence note (≤3 lines), and three audit items — explain (describe the data flow without looking at the code), change (hand-modify a requirement and predict the result first), catch (one AI mistake or rejected approach). See `docs/review/README.md`.
- **No course material in this repo.** The course is paid content; this public repo carries only our implementation and our own notes. See `docs/notes/README.md`.
- **API keys come from the environment only** — never committed, never pasted into chat. First provider: DeepSeek (OpenAI-compatible); see `docs/adr/0003-openai-compatible-first.md`.
- Module path: `github.com/Tangzy0121/mewcode-go`. Go toolchain is on the machine PATH.
- Plan and milestones: `docs/roadmap.md`. Decision records: `docs/adr/`.
- Do not reuse v0 (`Tangzy0121/mewcode-v0`) code or docs; it is a comparison artifact only. See `docs/adr/0001-restart-as-mewcode-go.md`.
