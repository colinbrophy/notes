# Project-Centred Wayland Workspace Manager

## Idea

Build a thin project layer for Wayland that treats a **project** as the main desktop object.

A project groups:

- application windows
- terminal sessions
- background services
- working directories
- layouts

Applications stay independent. Firefox remains Firefox, Ghostty remains Ghostty, and Neovim remains Neovim. This is not an IDE or a full-screen container.

## Core model

```text
Project: website
├── Firefox
├── Ghostty
│   └── tmux session: website
├── database client
└── development services
```

A project has identity and lifecycle. A workspace is only one graphical view of it.

## Commands

```bash
project open website
project switch website
project list
project close website
```

## First implementation

Use Sway because it has a mature IPC and predictable window control.

The first version should:

1. Read a small TOML project file.
2. Create or select a named Sway workspace.
3. Create or attach a matching tmux session.
4. Launch configured applications.
5. Move their windows to the project workspace.
6. Start configured systemd user services.

## Example manifest

```toml
name = "website"
directory = "~/src/website"
workspace = "website"
tmux_session = "website"

applications = [
  ["ghostty", "-e", "tmux", "attach", "-t", "website"],
  ["firefox", "http://localhost:3000"]
]

services = ["website.target"]
```

## Design principles

- mechanism over policy
- ordinary applications, not embedded panels
- project identity separate from workspace layout
- tmux owns terminal continuity
- systemd owns background services
- Sway owns window placement
- the project layer only coordinates them

## Longer-term direction

Prototype on Sway, but keep the internal model compositor-independent.

River may later be a better architectural home because its window-management policy can live in a separate programme.

## MVP success test

Selecting a project should make its windows appear, attach its terminal session, and start its services with one command.
