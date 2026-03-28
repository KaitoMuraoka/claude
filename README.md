# .claude

My global configuration directory for Claude Code.

## Setup

Replace your existing `~/.claude` with this repository.

Backup existing ~/.claude if present

```sh
mv ~/.claude ~/.claude.bak
```

Clone the repository as ~/.claude

```sh
git clone https://github.com/KaitoMuraoka/claude.git ~/.claude
```

## File Structure

```
~/.claude/
├── CLAUDE.md                 # Global instructions for Claude
├── settings.json             # Global settings (editor, statusline, plugins)
├── statusline-command.sh     # Custom statusline script
├── plans/                    # Plans directory
└── plugins/                  # Installed plugins
```

## Configuration

### `settings.json`

- **Editor**: `emacsclient --nw`
- **Status line**: Custom display via `statusline-command.sh`
- **Plugins**: `swift-lsp` (Swift LSP support)

### `statusline-command.sh`

Displays the following in the terminal status line:

- Current directory name (cyan)
- Git branch (yellow/red)
- Active model name (magenta)
- Context usage percentage (yellow at 50%+, red at 80%+)

### `CLAUDE.md`

Global instructions for Claude, applied across all projects.

### `plugins/`

Plugin management directory. Currently installed:

| Plugin | Version | Description |
|---|---|---|
| `swift-lsp` | 1.0.0 | Swift LSP support |

## Excluded Files (`.gitignore`)

The following are excluded for privacy and security reasons:

- `.credentials.json` — credentials
- `projects/` — per-project conversation data
- `*.jsonl` — conversation history
- `cache/`, `backups/`, `sessions/` — temporary and cache data
- `session-env/`, `shell-snapshots/` — runtime temporary data
- `settings.local.json` — local settings overrides
