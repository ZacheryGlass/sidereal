# Sidereal: Git Graph, Log & Worktrees

A free Git graph, log and file history, modeled on TortoiseGit's log view, with worktrees and submodules built in. Use it in VS Code or as a standalone app for macOS, Windows and Linux. No account, no ads, no telemetry.

![Opening the graph, scrolling the history, and opening a commit's diff](https://raw.githubusercontent.com/ZacheryGlass/sidereal/main/media/hero.gif)

[Install from the Marketplace](https://marketplace.visualstudio.com/items?itemName=zglass.sidereal) · [Open VSX](https://open-vsx.org/extension/zglass/sidereal) · [Download the app](https://github.com/ZacheryGlass/sidereal/releases/latest) · [Report an issue](https://github.com/ZacheryGlass/sidereal/issues) · [Discussions](https://github.com/ZacheryGlass/sidereal/discussions) · [Changelog](https://github.com/ZacheryGlass/sidereal/blob/main/CHANGELOG.md)

## Why Sidereal

- **Free.** Every feature, for personal and business use. There is no paid tier.
- **No account.** Nothing to sign in to.
- **No ads, no telemetry.** Sidereal makes no network requests of its own: the only network traffic comes from the Git commands you start, such as fetch, pull and push (and the standalone app's check for updates).
- **Maintained.** Fixes and features ship regularly; the [changelog](https://github.com/ZacheryGlass/sidereal/blob/main/CHANGELOG.md) lists every release.
- **Built for large histories.** Commits stream in as `git log` runs and only the visible rows are drawn. On a 100,000-commit repository the first 5,000 commits show in about half a second ([benchmark](https://github.com/ZacheryGlass/sidereal/blob/main/media/benchmark.json)).

## Screenshots

The graph with the References side bar (dark and light themes):

![The commit graph beside the References side bar, which lists branches, worktrees and submodules](https://raw.githubusercontent.com/ZacheryGlass/sidereal/main/media/graph-dark.png)

![The same graph in the Light Modern theme](https://raw.githubusercontent.com/ZacheryGlass/sidereal/main/media/graph-light.png)

A commit's details and one of its files' diff:

![Commit details below the graph, with a diff open beside it](https://raw.githubusercontent.com/ZacheryGlass/sidereal/main/media/commit-details.png)

Worktrees: other worktrees' branches are marked in the graph, and each opens in a new window or its own Sidereal tab:

![A worktree branch's menu in the graph, with the Worktrees group in the side bar](https://raw.githubusercontent.com/ZacheryGlass/sidereal/main/media/worktrees.png)

A submodule pointer change opens the submodule's history for exactly that range:

![A commit that updates a submodule, beside the submodule's history filtered to the new commits](https://raw.githubusercontent.com/ZacheryGlass/sidereal/main/media/submodule.png)

Filters by path, author, message, date, revision range, SHA and refs:

![The filter bar showing the commits that touched src/render/ since September](https://raw.githubusercontent.com/ZacheryGlass/sidereal/main/media/filters.png)

## Features

- **Commit graph** in an editor tab per repository, or in the bottom panel. Commits stream in as they load, the header row stays in view while scrolling, and runs of commits are collapsed by default.
- **Commit details** beside or below the list: changed files, diffs, file history, blame, git notes and `git describe`.
- **Commit form** for the working tree changes: stage or unstage files one by one or all at once, write a summary and description, amend the last commit or add a Signed-off-by, then **Commit** or **Commit & Push**.
- **Git actions** through VS Code's own prompts: checkout, branch, merge, rebase (including interactive), cherry-pick, revert, reset, tag, stash, notes, push, pull and fetch. Patches can be generated and applied; branches and tags have managers; the reflog is one menu away.
- **Filters**: path, author, message, SHA, refs, date range and revision range, plus first-parent, no-merges, follow-renames and a compressed graph. Jump between merges.
- **Worktrees**: see which branches other worktrees have checked out, create a worktree from any branch or commit, open it in a new window, the current window or its own Sidereal tab, and move uncommitted changes between worktrees.
- **Submodules** nested under their parent repository. A pointer change shows its commit range and opens the submodule's history for it; out-of-date submodules have an inline **Update**.
- **Issue linking**: rules in settings, or the bugtraq settings from a TortoiseGit `.tgitconfig`, turn issue numbers in commit messages into links.
- Follows your color theme, and the repositories open in Source Control.

## How it compares

As of October 2026, from each extension's Marketplace listing, issue tracker and pricing page:

| | Sidereal | [Git Graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph) | [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens) |
|---|---|---|---|
| Price | Free | Free | Commit Graph and worktrees free for public and local repositories ([pricing](https://www.gitkraken.com/gitlens/pricing)) |
| Last release | October 2026 | April 2021 | October 2026 |

Git Graph's open feature requests that Sidereal already covers:

| Request | Upvotes | Sidereal |
|---|---|---|
| [Filter the graph by file or folder (#70)](https://github.com/mhutchie/vscode-git-graph/issues/70) | 78 | **Paths** in the filter bar |
| [Keep the header visible while scrolling (#132)](https://github.com/mhutchie/vscode-git-graph/issues/132) | 33 | The header row stays in view |
| [Display git notes (#475)](https://github.com/mhutchie/vscode-git-graph/issues/475) | 19 | Notes in the commit details, and a filter that searches them |
| [Create and apply patches (#538)](https://github.com/mhutchie/vscode-git-graph/issues/538) | 17 | **Generate Patches** and **Apply Patches...** |

VS Code's built-in Source Control Graph shows commits, branches, and incoming or outgoing work. Sidereal adds the commit details, filters, worktrees and submodules around that history.

## Coming from Git Graph

- Open the graph with **Sidereal: Open Sidereal View**, the Sidereal button in Source Control's title bar, or the Sidereal icon in the activity bar.
- The Repo and Branches dropdowns, the commit details view and the right-click menus work the way you expect; filters live behind the funnel button.
- Requests that stayed open in Git Graph's tracker are here: filtering by path, notes, patches and a pinned header row.

## Coming from TortoiseGit

- The graph is TortoiseGit's Show Log: the same Graph, Actions, Message, Author and Date columns, the same reference label colors, and the **All Branches**, **Show Whole Project**, **Walk Behavior** and **View** controls below the list.
- Your `.tgitconfig` bugtraq settings link issues in commit messages, once you allow them for the repository.
- Branch, merge, rebase, cherry-pick, revert, reset, stash, tag, patch and reflog actions are in the same right-click menus.

## FAQ

**Is there a maintained alternative to Git Graph for VS Code?**
Sidereal is a free Git graph that ships regular updates, with a public [issue tracker](https://github.com/ZacheryGlass/sidereal/issues).

**How do I see a Git graph in VS Code?**
Install Sidereal and run **Sidereal: Open Sidereal View** from the Command Palette, or click the Sidereal icon in the activity bar.

**Does Sidereal need a GitKraken, GitHub or Microsoft account?**
No. There is nothing to sign in to.

**Does Sidereal collect telemetry?**
No. It makes no network requests of its own, besides the standalone app's check for updates.

**Is Sidereal free for commercial use?**
Yes. The license allows personal and internal business use at no cost.

**Is Sidereal open source?**
No. The source is private; [issues](https://github.com/ZacheryGlass/sidereal/issues) and [discussions](https://github.com/ZacheryGlass/sidereal/discussions) are public.

**How do I see Git worktrees in VS Code?**
Sidereal's References side bar lists every worktree, and the graph marks the branches and commits other worktrees have checked out. Worktrees open in a new window, the current window or their own Sidereal tab.

**How do I see a submodule's history in VS Code?**
Submodules are nested under their parent repository. Clicking a submodule pointer change in a commit's details opens the submodule's history for that range in its own tab.

**How do I filter Git history by folder or file?**
Open the filter bar (the funnel button) and enter paths such as `src/` or `README.md`. **View File History** on a file in the Explorer does the same for one file.

**Which versions does Sidereal need?**
VS Code 1.74 or later and Git 2.33 or later.

**Does Sidereal run without VS Code?**
Yes. The [standalone app](#standalone-app) runs on macOS, Windows and Linux.

**Does Sidereal work in VSCodium?**
Yes. Install it from [Open VSX](https://open-vsx.org/extension/zglass/sidereal), where VSCodium finds its extensions. Each release is checked in VSCodium: the graph, commit details and diffs, filters, the context menus, worktrees and submodules.

## Getting started

Run **Sidereal: Open Sidereal View** from the Command Palette, or click a branch in the Sidereal side bar, which lists branches, remotes, tags, stashes, worktrees and submodules. The graph opens in an editor tab; set **Sidereal: Open In** to **Panel** to open it in the bottom panel instead.

### Tabs and repositories

- Each repository gets one tab: opening a repository that has a tab reveals it. **Open in New Tab** is on each repository in the Repo dropdown, on repository nodes in the side bar, and in the Command Palette (**Sidereal: Open Repository in New Tab**).
- Picking a repository in a tab's Repo dropdown switches that tab, unless another tab already shows it: that tab is revealed instead.
- Side bar actions (show a branch, file history, fetch) go to the tab showing their repository, else the most recently used tab.
- Tabs are titled by how their repository relates to the workspace: `app`, `app › lib` (submodule), `app [feature]` (linked worktree), `tool (external)`. They reopen after a restart.
- The Repo dropdown groups repositories by workspace folder, then external ones, with submodules and worktrees nested under their repository.
- **Add Git Repository...** accepts any folder in a Git repository, also outside the workspace; it stays listed until removed.

## Settings

| Setting | Default | Description |
|---|---|---|
| `sidereal.openIn` | `Editor Tab` | Where the graph opens: `Editor Tab` or `Panel` (the bottom panel). |
| `sidereal.graph.branchColors` | theme colors | Colors of the graph's branch lines. |
| `sidereal.referenceLabels.showAheadBehind` | `true` | Show how far each branch is ahead of or behind its upstream. |
| `sidereal.commitDetails.describe` | `All Tags` | Which references describe a commit in its details. |
| `sidereal.documents.editorGroup` | `Active` | Editor group for files and diffs opened from Sidereal. |
| `sidereal.issueLinking.rules` | none | Rules that turn text in commit messages into links. |
| `sidereal.issueLinking.tortoiseGitSettings` | `Ask` | Whether a repository's TortoiseGit bugtraq settings apply. |
| `sidereal.repository.searchDepth` | `0` | Subfolder depth searched for repositories when VS Code's Git extension is off. |

## Standalone app

Sidereal also runs without VS Code, as an app for macOS 12 or later (Apple silicon and Intel), Windows 10 or later (x64 and Arm) and Linux (x64). Download it from the [latest release](https://github.com/ZacheryGlass/sidereal/releases/latest): the `.dmg` for macOS; for Windows, the `Sidereal-Setup` installer, or a `.zip` to unpack anywhere; for Linux, the `.AppImage`. It needs Git 2.33 or later installed.

- Each repository opens in a tab: from **File > Open Repository** or **New Tab**, a folder dropped on the window or the app's icon, a submodule or worktree in the graph, or `sidereal [folder]` in a terminal (**File > Install sidereal Command**).
- Diffs open in your diff tool and conflicts in your merge tool: Git's, or the one chosen in **Settings** (Beyond Compare, FileMerge, Meld and more). With none set, the app asks which of the installed ones to use. Blame and browsing a revision's files are only in the extension.
- At start, the app asks GitHub whether there is a newer version, and nothing else; **Settings** turns that off. The installed Windows app and the AppImage update themselves; the macOS app and the Windows zip say when a new version is out.
- An unsigned build is blocked on first launch. On macOS 15 or later, open the app, then choose **Open Anyway** in **System Settings > Privacy & Security**; on earlier versions, right-click the app in Finder and choose **Open**. On Windows, choose **More info > Run anyway**. On Linux, make the AppImage executable first (`chmod +x Sidereal-*.AppImage`).

### Extension vs. standalone app

| Feature | VS Code | Standalone | Notes |
|---|:-:|:-:|---|
| **Graph and views** | | | |
| Commit graph: streaming load, header row stays in view, collapsed runs | ✅ | ✅ | |
| A tab per repository | ✅ | ✅ | |
| Repos dropdown | ✅ | ✅ | |
| Filters: path, author, message, SHA, refs, dates, ranges | ✅ | ✅ | |
| Graph in the bottom panel | ✅ | ❌ | |
| Side bar with branches, remotes, tags, stashes, worktrees, submodules | ✅ | ❌ | The app shows these only in the graph |
| **Commit details** | | | |
| Changed files, git notes, `git describe` | ✅ | ✅ | |
| A file's log ("Show log") | ✅ | ✅ | |
| File diffs | ✅ | ✅ | The app opens them in your external diff tool |
| Open a file at a revision | ✅ | ✅ | The app opens a temporary copy in the file's default app |
| Conflicted files | ✅ | ✅ | The app opens them in your merge tool |
| External directory diff, with tool setup | ✅ | ✅ | The app saves the tool in its own settings, not Git's config |
| Blame | ✅ | ❌ | |
| Browse a revision's files | ✅ | ❌ | |
| Unified diff of a commit (patch view) | ✅ | ❌ | |
| **Actions** | | | |
| Commit form | ✅ | ✅ | |
| Checkout, branch, merge, rebase (incl. interactive), cherry-pick, revert, reset, tag, stash, notes, push, pull, fetch | ✅ | ✅ | The app asks for input inside the page instead of VS Code's prompts |
| Create and apply patches | ✅ | ✅ | |
| Create worktrees, open one in a Sidereal tab | ✅ | ✅ | |
| Open a worktree in a new or the current VS Code window | ✅ | ❌ | The app opens it in a tab instead |
| Move uncommitted changes between worktrees | ✅ | ❌ | Needs VS Code's Git extension |
| Submodules nested under their parent, with **Update** | ✅ | ✅ | |
| Issue linking | ✅ | ✅ | |
| Open in terminal | ✅ | ✅ | The app opens the system terminal |
| **Integration** | | | |
| Picks up the repositories open in Source Control | ✅ | ❌ | |
| Command Palette, Explorer's **Open Git Log**, **Open Source Control View** | ✅ | ❌ | |
| Open by dropping a folder, `sidereal [folder]`, or a start screen with recent repositories | ❌ | ✅ | |
| Follows the theme | ✅ | ✅ | The app follows system light/dark, or the theme set in Settings |
| Settings | ✅ | ✅ | The app has its own Settings dialog |
| Automatic updates | ✅ | ✅ | The installed Windows app and the AppImage update themselves from GitHub releases; the macOS app and the Windows zip say when one is out |
| Linux | ✅ | ✅ | The app is an x64 AppImage |

## About this repository

This repository holds Sidereal's [issue tracker](https://github.com/ZacheryGlass/sidereal/issues), [discussions](https://github.com/ZacheryGlass/sidereal/discussions), [changelog](CHANGELOG.md), [releases](https://github.com/ZacheryGlass/sidereal/releases) (the extension's VSIX and the standalone app's downloads) and images. Sidereal's source code is private.

## License

Free for personal and internal business use. Proprietary; see LICENSE.txt and ThirdPartyNotices.txt in the extension's folder, or **Help > License** and **Help > Third-Party Notices** in the standalone app.
