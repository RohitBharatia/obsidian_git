# obsidian-git

Sync your Obsidian vault markdown files to GitHub automatically.

## Features

-  Sync markdown files from your Obsidian vault to a GitHub repository
-  Track changes with meaningful commit messages
-  Secure credential handling with `.env` files
- ️ Configurable sync strategies (push, pull, bidirectional)
- ️ Conflict detection and resolution

## Installation

### Requirements
- Python 3.9+
- [UV package manager](https://docs.astral.sh/uv/)

### Setup

```bash
# Clone the repository
git clone https://github.com/yourusername/obsidian-git.git
cd obsidian-git

# Create virtual environment and install dependencies
uv sync
```

## Configuration

Create a `.env` file in the project root:

```env
GITHUB_TOKEN=<your_github_personal_access_token>
GITHUB_REPO=<yourusername/your-repo-name>
VAULT_PATH=</path/to/your/obsidian/vault>
SYNC_BRANCH=<main>
```

### Getting a GitHub Token

1. Go to GitHub Settings → Developer settings → Personal access tokens
2. Create a new token with `repo` scope
3. Copy the token to your `.env` file

## Usage

### Manual Sync

```bash
uv run python vault_sync/main.py --mode push
```

### Modes
(under development)

- `push` — Commit local changes and push to GitHub
- `pull` — Fetch latest from GitHub and merge locally
- `sync` — Bidirectional sync (experimental)

## Project Structure

```
obsidian_git/
├── vault_sync/
│   ├── config.py           # Configuration & env loading
│   ├── vault_scanner.py    # Detect vault changes
│   ├── git_handler.py      # GitHub API & git operations
│   ├── sync_logic.py       # Core sync strategies
│   ├── state_manager.py    # Track sync state
│   └── main.py             # CLI entry point
├── .gitignore
├── .gitignore.local
├── pyproject.toml
└── README.md
```

## Development

### Running Tests

```bash
uv run pytest
```

### Code Quality

```bash
# Format
uv run black vault_sync/

# Lint
uv run ruff check vault_sync/

# Type check
uv run mypy vault_sync/
```

## Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE.md) file for details.

## Support

For issues, questions, or feature requests, please open an [issue](https://github.com/yourusername/obsidian-git/issues) on GitHub.

## Roadmap

- [ ] Bidirectional sync with conflict resolution
- [ ] Scheduled syncing (cron integration)
- [ ] Obsidian plugin wrapper
- [ ] Support for encrypted vaults
- [ ] Sync filtering (ignore patterns)