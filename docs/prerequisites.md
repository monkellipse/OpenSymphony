### Prerequisites

#### Rust 1.97.1 or newer

**macOS / Linux**
1. Visit [rustup.rs](https://rustup.rs/).
2. Copy the install command shown on that page.
3. Run it in Terminal and follow the prompts.
4. Run `rustup update stable`.
5. Open a new terminal window after installation.
6. Verify the installation with `rustc +stable --version`.

**Windows**
1. Visit [rustup.rs](https://rustup.rs/).
2. Download the Windows installer shown there.
3. Run it and follow the prompts.
4. Run `rustup update stable`.
5. Open a new PowerShell or Command Prompt window after installation.
6. Verify the installation with `rustc +stable --version`.

OpenSymphony 2.11.0 and newer require Rust 1.97.1. The repository pins that
toolchain in `rust-toolchain.toml`, and published packages declare the same
minimum through `rust-version`.

---

#### Python 3.13.12 with `uv` for the OpenHands server

**Recommended path on macOS, Windows, and Linux**
1. Visit the [uv installation docs](https://docs.astral.sh/uv/getting-started/installation/).
2. Follow the instructions there to install `uv` for your platform.
3. Install Python 3.13.12 with `uv python install 3.13.12`.
4. Verify `uv` with `uv --version`.
5. Verify Python with `python3.13 --version`, or the equivalent command on your platform.

**Alternative**
If you already have Python 3.13.12 installed, you can keep it and just install `uv`. If you need a manual Python installer, use the official [Python downloads page](https://www.python.org/downloads/).

---

#### Node.js for ACP agents (conditional)

Only needed if you run an OpenHands `ACPAgent` (`openhands.conversation.agent.kind:
ACPAgent`) whose `acp_command` is an npm-published ACP server. The default
native OpenHands agent needs no Node.

The minimum version is set by the ACP server package, not by OpenSymphony:

| ACP server | Declared `engines.node` |
|------------|-------------------------|
| `@agentclientprotocol/claude-agent-acp` | `>=22` |
| `@google/gemini-cli` | `>=20` |
| `@zed-industries/codex-acp` | none declared |

1. Install Node from [nodejs.org](https://nodejs.org/) or a version manager such
   as [nvm](https://github.com/nvm-sh/nvm) or [fnm](https://github.com/Schniz/fnm).
2. Verify with `node --version`.
3. Make sure that version is on the PATH **of the process that starts the
   OpenHands agent-server**, not just your interactive shell — `npx` inherits
   the server process's environment.

A Node older than the ACP server's floor fails at the ACP handshake with a
`Connection closed` crash rather than a version error, because npm does not
enforce `engines` by default. See
[ACP server runtime requirements](configuration.md#acp-server-runtime-requirements).

<!-- BEGIN OPENSYMPHONY MANAGED MEMORY SYNC -->

## Current model

- COE-530 contributed: PR #193: docs(installer): document desktop installer validation (merge `7588cc7`)

## Important invariants

- Preserve the behavior described in the recent captured changes unless current code and tests show it has changed.
- Use capsule source refs to inspect the original PR or Linear issue when context is ambiguous.

## Operational flow

- No generated diagram requested for this sync.

## Known gotchas

- No area-specific gotchas were inferred from the selected memory.

## Recent changes

- COE-530: Installer Docs And End-To-End Validation

## Source refs

- COE-530

<!-- END OPENSYMPHONY MANAGED MEMORY SYNC -->
