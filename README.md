# Conduit

**Conduit** is a Windows desktop app for running [Claude Code](https://claude.com/claude-code) with several accounts side by side, for example a work account and a personal one. Each account keeps its own login, history, settings and MCP servers, and nothing leaks between them. Sessions run on the Claude Code CLI you already have installed.

This repository holds only the installers and update files. There's no source code here.

## Install

1. Open the [latest release](https://github.com/Eros/Conduit-releases/releases/latest).
2. Download `Conduit_<version>_x64-setup.exe` and run it. It installs for your user and doesn't need admin rights.

The installer isn't code-signed yet, so Windows SmartScreen may say it "prevented an unrecognised app from starting". Click **More info**, then **Run anyway**.

**You need:** Windows 10 or 11 (x64), and [Claude Code](https://docs.claude.com/en/docs/claude-code/setup) installed and on your `PATH`. Conduit warns you if your CLI version differs from the one it was tested with.

## Features

### Accounts and sessions
- **Separate accounts.** Each account gets its own Claude Code config folder, and every session runs with only that account's credentials. You can sign in from inside the app.
- **Workspaces and tabs.** Group sessions into workspaces, each locked to one account. Tabs are colour-coded and can be pinned and dragged. Split view shows up to four sessions at once, from any workspaces.
- **Live sessions.** Replies stream in as they're written, with tool calls rendered inline. Stopping a session interrupts the turn but keeps its context, and sessions pick up where they left off after a restart.
- **History and import.** See past conversations, and import your existing Claude Code sessions into the right account.
- **Search.** Full-text search across the prompts and replies of every account.
- **Model and effort per session.** Pickers show exact model versions, and changes apply straight away, even mid-session.
- **Message box.** Paste or drop images, `@`-mention project files, use `/` for saved prompts, and use **Send later** to queue a message for when your 5-hour limit resets.

### Reviewing changes
- **Attention queue.** Tool calls that need approval from any session, on any account, appear in one place. Approve, approve and remember, or deny with a reason.
- **Changes panel.** See the diff since the session started, unified or side by side, and accept or decline per block or per file. You can leave comments on blocks and send them to Claude as one review, and filter or auto-accept file types such as images and lock files.
- **Checkpoints.** Before each message, Conduit snapshots your working tree without touching your index or branches, so you can roll files back.
- **Worktree per session.** Optionally run a session on its own git branch and worktree, then merge, keep or discard it when you're done.
- **Commit and PR drafts.** Get a commit message and pull request description written from the diff. Conduit never stages, commits or pushes for you.

### Automation
- **Templates.** Start sessions from saved setups with a folder, worktree and opening message.
- **Send to several.** Send one prompt to several sessions and compare the results side by side.
- **Workflows.** Run a task through plan, execute and review stages, each with its own model, effort and prompt, with an optional pause to approve the plan.
- **Kanban board.** Cards run as sessions or workflows, with dependencies, priorities and limits. Auto mode starts Ready cards for you, and finished cards wait in Review for your approval.

### Project tools
- **CLAUDE.md editor.** Edit the project, local and account CLAUDE.md files, and see which skills, agents, slash commands and hooks Claude Code loads for the project.
- **MCP manager.** Manage account, project and local MCP servers, turn them on or off per workspace, and limit servers that can't be shared (such as Unity) to one session at a time.

### Usage and personalisation
- **Analytics.** Tokens and API-equivalent cost per account by day, plus plan usage meters.
- **Usage alerts.** In-app and Windows notifications when you near your plan-window or daily cost thresholds.
- **Themes.** 13 built-in themes, including Nord, Dracula, Tokyo Night, Catppuccin, Gruvbox and Solarized, each with matching code colours. You can also make and share your own.
- **Plugins.** A plugin is a single JSON file that adds themes, prompts, workflows, presets or sandboxed panels. Conduit shows each plugin's permissions and SHA-256 before installing. Plugins can't run commands, reach the network or send messages.
- **Notifications.** A completion sound and Windows notifications when a session finishes or needs you. Keyboard shortcuts for the common actions are listed under `Ctrl+/`.

## Updates

Conduit checks here for new versions when it starts, and in **Settings > About**. It only installs updates signed with its release key, and only when you choose to.

## Your data

Everything stays on your PC: Conduit keeps its database and search index in `%USERPROFILE%\.conduit`, and your accounts' Claude Code folders hold their logins and history. Conduit talks to Claude only through the Claude Code CLI.

Conduit is an independent project. It isn't made by or affiliated with Anthropic.
