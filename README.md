# Obsidian Github linking

### About
This project is to be able to link and git vc an obsidian vault without needing a plugin.
It should be more lightweight than most other available options. This is still a work in progress and 
once it is finished, it will be rewritten in C++.

# Project setup

Currently, the project is in a development stage. In the dev state, to build the current project, you can use:
```bash
uv venv
uv sync
source .venv/bin.activate
```
 

The ideal file structure would be:

```html
obsidian_git/
├── .venv/
├── vault_sync/
│   ├── __init__.py
│   ├── config.py
│   ├── git_handler.py
│   ├── vault_scanner.py
│   ├── sync_logic.py
│   ├── state_manager.py
│   └── main.py
├── .gitignore
├── .gitignore.local
├── pyproject.toml
├── uv.lock
└── README.md
```