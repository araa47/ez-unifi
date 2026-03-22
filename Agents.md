# Agent Guidelines

- Use `uv` for all dependency management (`uv add`, `uv run`). Never use `requirements.txt`.
- Python 3.10+. Use modern type annotations (`list`, `dict`, not `List`, `Dict`).
- Before committing: run `prek run --all-files`. All hooks must pass.
- Skill files live in `skills/ez-unifi/` — that's what gets installed via `npx skills add` or `clawhub install`.
