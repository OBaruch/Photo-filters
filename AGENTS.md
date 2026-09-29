# AGENTS.md

Guidelines for automated contributors (AI coding agents, bots and scripts) working in this repository.

## Repository Nature

This is a **historical repository**. It preserves an original MATLAB GUIDE project (see [README](README.md)). Its value is its authenticity, not its completeness.

## Hard Rules

1. **Do not modify `src/filtros.m`.** Do not fix, format, rename, modernize or reindent it. Its SHA-256 must stay `778a09112953e1be2804532b4d0788e8ca82b75574fe890441c47478b17bdc41`.
2. **Do not modify `LICENSE`.**
3. **Do not delete files.** When unsure, keep the file.
4. **Do not invent context.** Label claims as *Confirmed*, *Inferred* or *Unknown*.
5. **Do not add infrastructure** (CI/CD, Docker, build tools, test frameworks, linters) unless a human explicitly asks for it.
6. Write documentation in **English**.

## Workflow

Any non-trivial change follows **Intent → Spec → Plan**:

- [`docs/sdlc/intent.md`](docs/sdlc/intent.md): why the change is made and what is out of scope
- [`docs/sdlc/spec.md`](docs/sdlc/spec.md): what the change delivers and its acceptance criteria
- [`docs/sdlc/plan.md`](docs/sdlc/plan.md): the steps and how each one is verified

Update these documents when the scope changes. Work on a dedicated branch and submit changes through a pull request for human review.

## Verification Before Submitting

```bash
sha256sum src/filtros.m
git diff --diff-filter=D --name-only main   # must be empty
```
