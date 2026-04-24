# pi-file-search

Modern file and content search for pi. Combines `fd`, `ripgrep`, and `fzf` as both a **skill** (teaches bash commands) and **extension tools** (dedicated typed tools).

## Features

- **Skill**: Auto-triggers on "fd", "rg", "find files", "search code", "fzf", "fuzzy find"
- **Extension Tools**: `fd` and `rg` tools with typed parameters
- Respects `.gitignore` automatically
- Fast, modern alternatives to `find` and `grep`

## Requirements

```bash
# macOS
brew install fd ripgrep fzf

# Ubuntu/Debian
sudo apt install fd-find ripgrep fzf

# Arch
sudo pacman -S fd ripgrep fzf
```

## Install

```bash
pi install git:github.com/YOUR_USERNAME/pi-file-search
```

Or local development:
```bash
pi install ./pi-file-search
```

## Usage

The skill auto-loads when you mention file search tasks:

```
find all typescript files
search for TODO in the codebase
fuzzy find a file to edit
```

Or force-load:
```
/skill:file-search
```

Extension tools are available directly:
```
Use fd to find all config files
Use rg to search for "import React"
```

## Tools (Extension)

### fd
- `pattern`: Filename pattern
- `path`: Directory to search
- `extension`: Filter by extension (e.g., "ts")
- `type`: "file" or "directory"
- `exclude`: Patterns to exclude
- `hidden`: Include hidden files

### rg
- `pattern`: Search pattern (regex)
- `path`: Directory or file
- `extensions`: Filter by file types
- `ignoreCase`: Case-insensitive
- `context`: Lines of context
- `filesOnly`: Return filenames only
- `countOnly`: Return match counts
- `literal`: Treat as literal string

## Examples

```bash
# Find
fd pattern="*.config" extension="ts"
fd pattern="src" type="directory"

# Search
rg pattern="TODO" extensions=["ts","tsx"]
rg pattern="function" context=3 filesOnly=true
```

## License

MIT
