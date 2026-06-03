# Shell — Built in C++

A POSIX-compliant shell built from scratch in C++ as part of the
[CodeCrafters "Build Your Own Shell"](https://codecrafters.io/challenges/shell) challenge.

## What it does

Interprets shell commands, runs external programs, and implements
core built-in commands — without relying on any shell library.

## Built-in Commands

| Command | Description |
|---------|-------------|
| `echo` | Prints arguments to stdout |
| `exit` | Exits the shell with a status code |
| `type` | Identifies builtins or resolves executable paths |
| `pwd` | Prints the current working directory |
| `cd` | Changes directory — absolute, relative, and `~` |
| `history` | Lists command history with navigation support |
| `jobs` | Lists background jobs |
| `declare` | Declares and manages shell variables |

## Features

- **REPL loop** — Read, evaluate, print, repeat
- **Invalid command handling** — Graceful errors for unknown commands
- **PATH resolution** — Locates and executes any binary on `$PATH`
- **External program execution** — Spawns child processes via `fork()` + `execvp()`
- **Quoting** — Single quotes, double quotes, backslash inside/outside quotes, quoted executables
- **Redirection** — stdout (`>`), stderr (`2>`), append stdout (`>>`), append stderr (`2>>`)
- **Command completion** — Builtin completion, executable completion, filename/directory completion, partial and multi-argument completion
- **Programmable completion** — Register completions, handle missing specs, single/multiple candidates, longest common prefix
- **Background jobs** — Start, list, reap, recycle job numbers
- **Pipelines** — Dual-command, pipelines with builtins, multi-command pipelines
- **History** — List, limit entries, up/down arrow navigation, execute from history
- **History persistence** — Read/write/append history to file on startup and exit
- **Parameter expansion** — Store/expand variables, validate names, expansion with braces, empty variable handling

## Concepts Covered

- Process lifecycle: `fork()`, `execvp()`, `waitpid()`
- File descriptor manipulation for redirection and pipes
- Environment variable parsing (`$PATH`, `$HOME`, `$HISTFILE`)
- Shell quoting and escape rules (POSIX-compliant)
- Tab completion architecture
- Job control and background process management
- Command history with persistence

## Tech

- **Language:** C++17
- **Build:** CMake
- **Platform:** Linux / macOS

## Run Locally

```bash
git clone https://github.com/niishaparashar/shell-cpp
cd shell-cpp
mkdir build && cd build
cmake .. && make
./shell
```

## Progress

<details>
<summary><strong>Core</strong></summary>

- [x] Print a prompt
- [x] Handle invalid commands
- [x] Implement a REPL
- [x] `exit` built-in
- [x] `echo` built-in
- [x] `type` built-in
- [x] Locate executable files
- [x] Run a program

</details>

<details>
<summary><strong>Navigation</strong></summary>

- [ ] `pwd` built-in
- [ ] `cd` — absolute paths
- [ ] `cd` — relative paths
- [ ] `cd` — home directory (`~`)

</details>

<details>
<summary><strong>Quoting</strong></summary>

- [ ] Single quotes
- [ ] Double quotes
- [ ] Backslash outside quotes
- [ ] Backslash within single quotes
- [ ] Backslash within double quotes
- [ ] Executing a quoted executable

</details>

<details>
<summary><strong>Redirection</strong></summary>

- [ ] Redirect stdout
- [ ] Redirect stderr
- [ ] Append stdout
- [ ] Append stderr

</details>

<details>
<summary><strong>Command Completion</strong></summary>

- [ ] Builtin completion
- [ ] Completion with arguments
- [ ] Missing completions
- [ ] Executable completion
- [ ] Multiple completions
- [ ] Partial completions

</details>

<details>
<summary><strong>Filename Completion</strong></summary>

- [ ] File completion
- [ ] Nested file completion
- [ ] Directory completion
- [ ] Missing completions
- [ ] Multiple matches
- [ ] Partial completions
- [ ] Multi-argument completion

</details>

<details>
<summary><strong>Programmable Completion</strong></summary>

- [ ] Register complete builtins
- [ ] Printing missing specifications
- [ ] Displaying registered specs
- [ ] Single completion
- [ ] Handling no completions
- [ ] Passing command-line arguments
- [ ] Passing environment variables
- [ ] Multiple completer candidates
- [ ] Longest common prefix
- [ ] Unregister a completion

</details>

<details>
<summary><strong>Background Jobs</strong></summary>

- [ ] The jobs builtin
- [ ] Starting background jobs
- [ ] Printing background job status
- [ ] List a single job
- [ ] List multiple jobs
- [ ] Reap one job
- [ ] Reap multiple jobs
- [ ] Reap before the next prompt
- [ ] Recycle job numbers

</details>

<details>
<summary><strong>Pipelines</strong></summary>

- [ ] Dual-command pipeline
- [ ] Pipelines with built-ins
- [ ] Multi-command pipelines

</details>

<details>
<summary><strong>History</strong></summary>

- [ ] The history builtin
- [ ] Listing history
- [ ] Limiting history entries
- [ ] Up-arrow navigation
- [ ] Down-arrow navigation
- [ ] Executing commands from history

</details>

<details>
<summary><strong>History Persistence</strong></summary>

- [ ] Read history from file
- [ ] Write history to file
- [ ] Append history to file
- [ ] Read history on startup
- [ ] Write history on exit
- [ ] Append history on exit

</details>

<details>
<summary><strong>Parameter Expansion</strong></summary>

- [ ] The declare builtin
- [ ] Printing missing variables
- [ ] Storing shell variables
- [ ] Validating variable names
- [ ] Expanding variables
- [ ] Expansion with braces
- [ ] Expanding empty variables

</details>

## Reference

Built via [CodeCrafters](https://codecrafters.io) — a platform for
rebuilding real production tools from scratch.
