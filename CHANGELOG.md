# Changelog

## 1.3.0 - 2026-10-27

- Sidereal is also published to [Open VSX](https://open-vsx.org/extension/zglass/sidereal), and is tested in VSCodium.
- After the 10th time a graph opens, one message asks whether you'd rate Sidereal: **Rate** opens the Marketplace's review section, **Report an Issue** the issue tracker, and **Don't Ask Again** closes it. It never shows again, whatever the answer.
- The Marketplace listing is now **Sidereal: Git Graph, Log & Worktrees**, with screenshots and links to the public [issue tracker](https://github.com/ZacheryGlass/sidereal/issues), [discussions](https://github.com/ZacheryGlass/sidereal/discussions) and changelog.

## 1.2.0 - 2026-10-27

- Issue linking rules are now settings (`sidereal.issueLinking.rules`) in user, workspace or folder scope, so a team can share them in `.vscode/settings.json`. A repository can have several rules, each with an optional section regex.
- `sidereal.issueLinking.tortoiseGitSettings` (Ask, Always, Never) decides whether TortoiseGit's bugtraq settings apply. The bugtraq regex is derived from `bugtraq.message` when `bugtraq.logregex` is unset, and each of several comma-separated bug IDs becomes a link, as in TortoiseGit.
- The More Actions menu's issue linking items are now one **Issue Linking...** picker that shows which rules apply and where they come from.
- The commit table's header row stays in view while scrolling.
- **Open Git Log (Sidereal)** in the Explorer's folder context menu opens that folder's repository in a tab.
- **Remove Repository** is in the context menu of a repository in the side bar.
- The quick filter is hidden while the filter bar is open, and text typed into it carries over to the bar.
- A graph line moving to a freed column now steps between rows, instead of running along another commit's row.
- Fixed: a merge into a commit that a line turned into from the right could be drawn twice, with a stray line down to the last loaded row.
- Fixed: removing a branch from the Branches dropdown selection could fail to load the graph in a repository with many branches (the command line was too long).
- Fixed: **Add Rule to the Workspace Settings** wrote a folder's settings in a multi-root workspace.
- Fixed: switching a tab to another repository could briefly switch it back, and a tab moved to another window stopped following repository switches.
- Fixed: **Open Worktree in Sidereal Tab** and **View File History** could open no tab when VS Code's Git extension opened the repository at the same moment.
- Fixed: a worktree removed through VS Code's Git extension stayed listed in the References view, the Repo dropdown and its tab.
- Fixed: **Prune Worktrees...** missed worktrees whose folders had just been deleted.
- Fixed: after a restart, showing a reference could open a second tab for a repository whose restored tab VS Code had not revived yet.

## 1.1.0 - 2026-10-26

- One editor tab per repository, restored after a restart. **Open Repository in New Tab** is on the Repo dropdown, the side bar and the Command Palette.
- Tabs are titled by how their repository relates to the workspace: `app`, `app › lib` (submodule), `app [feature]` (linked worktree), `tool (external)`.
- **Add Git Repository...** accepts a repository outside the workspace.
- **Open Worktree in Current Window** and **Migrate Worktree Changes...**.
- Worktrees are added and removed through VS Code's Git extension when it has the repository open.
- The References view shows every group, with a placeholder when one is empty.

## 1.0.2 - 2026-10-26

- The graph opens in an editor tab by default. Set **Sidereal: Open In** to **Panel** to use the bottom panel.
- Double-click no longer checks out a branch or opens a worktree. Use the right-click menu.

## 1.0.1 - 2026-10-26

- Restored the TortoiseGit colors of the reference chips.

## 1.0.0 - 2026-10-26

First Marketplace release.

- Commit graph in an editor tab or the bottom panel. Commits stream in as `git log` runs, and only the visible rows are rendered.
- Commit details beside or below the list: changed files, diffs, file history, blame and patches.
- Git actions through VS Code's own prompts: checkout, branch, merge, rebase (including interactive), cherry-pick, revert, reset, tag, stash, notes, push, pull and fetch.
- Filters by message, author, path, SHA, refs, date range and revision range.
- Worktrees: other worktrees' branches and detached commits are marked in the graph, and worktrees can be created from the branch and commit menus.
- Submodules nested under their parent repository, with pointer changes shown in commit details and an inline **Update** for out-of-date submodules.
- The References side bar lists branches, remotes, tags, stashes, worktrees and submodules.
- Colors follow the VS Code theme.
