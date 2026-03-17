# Codex Agent Guidelines

## Docs & API references (Context7)

Always use Context7 MCP when I need library/API documentation, code generation, setup or configuration steps without me explicitly asking.

## Tooling

- Environment: ArchLinux on WSL2. 
- Shells: `bash` is the login shell; `fish` is the interactive shell.
- TypeScript: `fnm`, `pnpm`, `ESLint`, `typescript-eslint`, `Prettier`.
- Python: `uv`, `ruff`, `pyrefly`.
- Markdown: VS Code `markdownlint` and `markdownlint-cli2`.

## Scaffolding & Dependencies

- Prefer me manually run official init/create commands for scaffolding, dependency installation, and base config.
- If an init/create command is interactive, tell me what to run, what to expect, and which options to choose; then wait for me to finish.
- If new dependencies are needed, ask me to run the install command manually.

## Protected Files

- Never create, edit, or delete dependency definition files, lock files, or project/toolchain configuration files unless I explicitly ask for that class of change.
- This includes package/dependency manifests, lock files, compiler configs, build-system files, formatter/linter/test-runner configs, environment/toolchain selectors, and similar project-definition files across JavaScript/TypeScript, Python, Rust, Go, C/C++, and related ecosystems.
- Examples include `package.json`, `pnpm-lock.yaml`, `tsconfig*.json`, `pyproject.toml`, `uv.lock`, `requirements*.txt`, `Cargo.toml`, `Cargo.lock`, `rust-toolchain*`, `go.mod`, `go.sum`, `CMakeLists.txt`, `Makefile`, `meson.build`, `.clang-format`, `.clang-tidy`, and similar files.
- One exception is the `scripts` section of `package.json`.
- If such files need to change, stop, explain why, and ask me to do the edit or install step manually.

## Git Note

- You struggle with interactive `git rebase --continue`, use `GIT_EDITOR=true` with it.

## Git History Quality

- When reviewing a branch for merge, evaluate whether the commit history reflects durable project history or temporary review scaffolding.
- If the branch contains rename-only commits, temporary planning artifacts, vague commit messages, or iterative cleanup churn, prefer recommending a rewrite into a smaller set of higher-signal commits before merge.
- Do not default automatically to either keeping noisy history or squashing everything into one commit.
- When appropriate, preserve 2-3 meaningful phases as separate commits if they represent durable story beats.
- Prefer squash-on-merge mainly when the branch is mostly iterative noise or the repository intentionally follows a one-change-one-commit policy.
