# autocommit

A bash script that automatically generates commit messages using an LLM based on your code changes.

## What it does

Analyzes your git diff, looks at your previous commit messages to match your style, and generates an appropriate commit message using `llmcli`. Then commits the changes automatically.

## Requirements

[llmcli](https://github.com/artyom/llmcli) v0.7.0 or later.

## Usage

Either directly from within a git repository:

```bash
autocommit
```

Optionally provide extra context:

```bash
autocommit Fixes issue #123
```

The script will:

- Commit staged changes if any exist
- Otherwise commit all modified files (`git commit -a`)
- Exit if nothing to commit or if the situation is unclear

## Git alias setup

Add to your `~/.gitconfig`:

```
[alias]
    autocommit = !$HOME/path/to/autocommit
```

Then use it as:

```bash
git autocommit
git autocommit "Additional context here"
```

Adjust the path to wherever you placed the script.
