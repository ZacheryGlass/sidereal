# Changelog

## 1.7.0 - 2026-11-02

- **Resolve with AI...** in the conflict banner and on each conflicted file hands the conflicts to Claude Code, Codex or GitHub Copilot CLI, whichever you have installed. The agent resolves every conflict, saying which way it went where the two sides clash, and Sidereal marks each file as resolved. For a rebase, or a cherry pick or revert of several commits, it can carry on to the end: it continues after each commit and resolves the next one's conflicts the same way, stopping at any it leaves unresolved. It then says how it went and what is left to do, with what it did in each commit and what the agent said collapsed below. Files both sides deleted are marked as resolved without the agent. A merge's commit stays yours. If the custom AI command in Settings can't run, the dialog says why. Everything is asked and reported in Sidereal's own dialogs, and **Next time, start without asking** skips the question (`sidereal.conflicts.confirmResolveWithAI`, `sidereal.conflicts.aiAgent`). `sidereal.conflicts.resolveWithAI` hides it.
- When a merge, rebase, cherry pick, revert, pull, or an applied stash or patch stops on conflicts, the graph says so in plain words, with **Resolve with AI** (and a choice of agent) and **Resolve Myself**, instead of showing Git's output as an error. With **Always resolve with AI without asking** on, the agent starts right away.
- Settings has an **AI Features** section (**Sidereal › AI** in VS Code) that shows the command each agent runs. Choose **Other** to run a command of your own, with `{prompt}` where the prompt goes, for example `aider --yes --message {prompt}`. These are user settings only, so a repository's workspace settings can't choose what runs.
- **Drag and drop in the graph**: drag a branch label onto another commit or branch to rebase it there, even a branch that isn't checked out, or onto the checked-out branch to merge it. Drag commits (or a selection) onto the checked-out branch to cherry-pick them. Each drop opens a menu of what it can do; a merge's dialog confirms, and a rebase or cherry pick is planned in the graph. Resting on a target previews the result in the graph, with the commits being moved highlighted and collapsed runs kept collapsed, and every change is animated.
- **Delete Worktree Folder...** in the graph's menu for another worktree's branch deletes that worktree after confirming. It stops instead while the worktree has uncommitted changes or untracked files.
- **Standalone app**: Show Log and Fetch in the file manager's right-click menu, as in TortoiseGit. Show Log on a file or folder shows its history.
- **Standalone app**: the **+** button (and **File > New Tab**) opens a New Tab dialog with your favorite and recent repositories. Type to filter, pin a repository to keep it in Favorites, or choose **Open Folder...** for any other.
- **Standalone app**: on Windows, the tab strip is the window's title bar, as on macOS, instead of sitting below a title bar and a menu bar. The window's buttons sit at its right end in the app's light or dark colors, and the menu opens from the button at its left, or with Alt or F10.
- **Standalone app**: after a few days of use, Sidereal asks once whether you'd star it on GitHub. **Help > Sidereal on GitHub** opens the repository, and after an update to a new minor version a message links to its release notes. The **About** section of Settings links to Sidereal's website, its repository, its Marketplace and Open VSX pages, the changelog and the new issue page.
- **Report an Issue** in the message asking for a rating, and in the standalone app's **Help** menu, opens the new issue page, as the command does, instead of the list of issues.
- The filter button opens the filter options in a panel over the graph, like the standalone app's Settings, instead of a bar above it. **Apply** and **Clear** close it.
- **Standalone app**: prompts, such as a new branch's name, have a close button that cancels them, like Escape. A list of choices shows its question above it instead of in a filter field, which only long lists of single choices have now.
- **Merge** asks in one dialog that lists the commits it brings in, with its options below them, instead of a series of prompts, in VS Code as in the standalone app. It shows whether it can fast-forward, and keeps **Don't commit** and the strategy options under **Advanced**. An option that doesn't apply with the others is turned off, its reason in its tooltip, and the dialog stays open while the view refreshes in the background.
- Every rebase is planned in the graph instead of a dialog: the graph shows the commits it replays where they will go, newest at the top, and a **Rebase** column slides out beside it with each commit's handle and action. They start all picked, ready to run as they are, or to drag into another order, reword, edit, squash, fix up or drop first (or press P, R, E, S, F or D), and the graph shows each change at once: a dropped or squashed commit loses its dot. A reworded or squashed commit's message is edited below its row. The banner above the graph, which stays in view as you scroll, says what the rebase does and holds **Change All to...**, **Rebase** and **Cancel**; Enter rebases and Escape cancels. It replaces the separate **Interactive Rebase** choice, and rebases a branch that isn't checked out too. **Ignore Date** is gone.
- While a rebase is under way, the graph keeps showing its commits the way it planned them, in the **Rebase** column: the commits made so far with a check, the one it stopped at (marked when on conflicts), and copies of those still to come on top. A step that made no commit of its own (skipped, or left with nothing to change) is named on the commit before it, and commits you make yourself at a stop, such as a commit split in two, stay in the band with that step. The banner shows how far it has got. For a cherry pick or revert of several commits, the banner lists those left. **Continue** (or **Resolve with AI...** while conflicts remain) stands out as the next step.
- **Cherry Pick** and **Revert** are planned in the graph instead of a dialog: the graph shows the commits they will add on top of the checked-out branch, and the banner above it, which stays in view as you scroll, says what they do and holds their options (**Record where it came from**, **Don't commit**, and for a merge commit the parent to apply it relative to) with **Cherry Pick** or **Revert** and **Cancel**. Enter starts it and Escape cancels. With **Don't commit**, the graph highlights the commits it applies instead. When the graph doesn't show the checked-out commit, the banner lists the commits.
- The buttons of the graph's dialogs can be reached with Tab and pressed with Enter or Space. In the merge dialog and the conflict overlay, Tab stays inside the dialog.
- The graph's SHA-1 column shows the first 8 characters of each hash instead of the full hash. Hover a hash to see it in full.
- **Standalone app**: releases no longer include the macOS and Windows zips. Download the `.dmg`, the `Sidereal-Setup` installer or the `.AppImage`.
- A rebase stopped on conflicts in a squash or fixup no longer says it stopped to edit the commit, and **Skip** asks about skipping the commit rather than its editing.
- A rebase whose plan was changed now drops a commit left with nothing to change, as one run as planned does, instead of stopping there. When the plan edits a commit, or squashes or fixes up commits, such a commit is kept (empty) instead, so the edit or the squash still applies to it rather than to the commit before it.
- When Sidereal fails unexpectedly while committing, merging, rebasing or cherry picking, the commit form's buttons work again afterwards, a dropped commit or branch no longer leaves its preview in the graph, and the Actions column keeps filling in as you scroll.
- A file's **Uncommitted** diff opened again after a commit compares with the new HEAD instead of the HEAD it was first opened with, and a conflict's **Ours ↔ Theirs** diff shows the current conflict's sides, not an earlier one's.
- A rebase being planned stays when a fetch in the background (VS Code's autofetch, a terminal) adds or prunes remote branches, or the graph refreshes, instead of losing the plan. It is cancelled when the checked-out branch or the local branches change.
- After `git submodule deinit` (or deleting a nested repository's `.git`), the folder left behind no longer hands its view state, such as its name, columns and issue linking, to the repository it is in, overwriting that one's.
- **Standalone app**: on Linux, **Open in Terminal** works without `x-terminal-emulator` (which only Debian and Ubuntu have): it tries `$TERMINAL`, then GNOME's, KDE's, Xfce's and other terminals, and xterm.
- **Standalone app**: tabs of repositories on a drive that isn't mounted when the app starts are no longer forgotten. They open again at a later start, once the drive is back.
- **Standalone app**: on Windows, a repository opened from **File > Open Repository** or by dropping its folder no longer opens a second tab when it is opened again another way, such as **Show Log** in Explorer, and is listed once in **Open Recent** and the New Tab dialog.
- **Standalone app**: binary files in a commit's details no longer show "+NaN −NaN" (and NaN in the totals), and no longer offer a diff that can't be shown.
- In VS Code, the graph picks up changes made outside VS Code as the standalone app does: Git commands run in a terminal, such as `git add` marking a conflict resolved, creating a branch or a tag or dropping a stash, and files changed by other programs. It no longer waits until you switch back to VS Code's window or press F5, and keeps refreshing in a repository with more than 10,000 changes.
- A change made right after another, such as a second `git add` a second after the first while the graph was still refreshing, or right after one of Sidereal's own actions, is no longer missed, leaving the graph showing a conflict already resolved.
- The graph no longer reloads after an install or a build writes more than 10,000 files into a folder Git ignores, such as `node_modules`.
- In a text field, such as the commit form's summary, Escape leaves the field instead of closing the commit details, and on macOS Ctrl+H deletes the character before the caret instead of jumping to HEAD.
- Switching repositories while the **Working tree changes** were loading no longer shows the previous repository's changes in the new one's details, where staging or committing would act on the wrong files.
- A commit that changes a file in a folder named `constructor`, `toString` or the like no longer leaves its details stuck on "Retrieving Commit Details ...". A branch of such a name no longer always counts as selected in **Manage Branches** (and so deleted with the selected ones), nor shows a worktree or upstream badge it doesn't have.
- Checking out a branch that was deleted meanwhile (in a terminal, say) no longer checks out the files of a folder of the same name instead, throwing away their uncommitted changes. It fails, saying the branch is gone.
- **Commit & Push** pushes to the branch's upstream only where `git push` would: a branch made from `origin/main` under another name no longer pushes its commits onto `main`, and a branch that pushes to another remote (`branch.<name>.pushRemote`, `remote.pushDefault`) no longer pushes to the one it fetches from. Sidereal asks where to push instead.
- A checked-out branch with a tag of the same name (a branch `v1` and a tag `v1`) is shown as checked out again in the References view, and named `v1` instead of `heads/v1` when an action stops on conflicts.
- Fetching a remote branch into a local branch, and pulling a remote branch, no longer take a tag of the same name on the remote instead (which left the branch's new commits unmerged and said "Already up to date").
- Deleting a branch on a remote no longer also deletes a tag of the same name there (or only the tag, once the branch is gone from the remote), and deleting a tag on a remote no longer deletes a branch of the same name.
- **Edit Remote...** no longer fails with "No such URL found" when the old URL has a character such as `+` or `?` in it, and removing a push URL no longer also removes the others that contain it.
- The **Sidereal** output log masks passwords and tokens in URLs, such as a remote's `https://user:token@host/repo.git`, so the log is safe to share in an issue.
- Sidereal uses the Git executable that `git.path` names after a restart too, instead of the one it used last, and switches to the one it finds itself once `git.path` is cleared.
- **Reset** (to a commit, or of the uncommitted changes) no longer starts on **Hard** because it was chosen last time, so one Enter can't throw away the uncommitted changes. It starts on **Mixed** instead.
- A repository without commits, such as one just created with `git init`, shows "This repository has no commits yet." in the graph instead of an error with a **Retry** that couldn't work. Its first commit shows up on its own.
- On an orphan branch (`git switch --orphan`), whose first commit isn't made yet, the graph shows the other branches' history instead of "Unable to Load Commits: fatal: bad revision 'HEAD'".
- **Standalone app**: a crash or a full disk while the app saves no longer empties its `state.json` or `settings.json`, which lost every tab, recent repository and setting. A file that can't be read is kept as `state.json.corrupt` (or `settings.json.corrupt`) instead of being overwritten.
- **Standalone app**: when something fails while the app starts, it says so and quits, instead of staying open (or running without a window) and ignoring every later **Show Log**, **Fetch** and `sidereal` request.

## 1.6.0 - 2026-10-30

- **Standalone app**: Sidereal also runs without VS Code, as an app for macOS 12 or later, Windows 10 or later and Linux (x64). Download it from the [1.6.0 release](https://github.com/ZacheryGlass/sidereal/releases/tag/v1.6.0). Each repository opens in a tab, diffs open in your diff tool and conflicts in your merge tool; the [README](https://github.com/ZacheryGlass/sidereal#standalone-app) compares it with the extension.
- **Show Release Notes**, **Open Sidereal on GitHub**, **Report an Issue** and **Rate Sidereal** are in the Command Palette, the References view's **...** menu and the **More Actions** menu.
- After Sidereal updates to a new minor version (for example 1.5 to 1.6), a message links to its release notes. **Don't Show Again**, or the `sidereal.showReleaseNotes` setting, turns it off.
- The rating message waits until the graph has opened 10 times on at least 3 different days. In editors that install from Open VSX, such as VSCodium and Cursor, **Rate** opens Open VSX instead of the Marketplace.
- Staging in the commit form, or running git in a terminal, no longer fails now and then with "index.lock: File exists" while Sidereal refreshes in the background.
- On Windows, **Launch External Directory Diff** no longer fails with "could not symlink" when comparing the checked-out commit.

## 1.5.0 - 2026-10-29

- **Collapse Runs of Commits** in the footer's **View** menu is now on by default.
- The **Launch External Directory Diff** button in the commit details is always shown. If Git has no diff tool set up, clicking it lists the tools installed on your computer and saves the one you pick to your global Git config (`diff.guitool`, or `diff.tool` for a terminal tool). **Sidereal: Configure External Diff Tool** in the Command Palette does the same.
- **Launch External Directory Diff** works on a repository's first commit.
- The **Working tree changes** open at once: Sidereal loads them in the background after the graph loads, then checks them again as they open.

## 1.4.0 - 2026-10-28

- **Commit...** opens a commit form in Sidereal instead of git's `COMMIT_EDITMSG` file. It has a summary and description, staged and unstaged files you can stage or unstage one by one or all at once, **Amend Last Commit** and **Add Signed-off-by**, and **Commit** or **Commit & Push** (Ctrl/Cmd+Enter commits). A failing commit hook shows its output.
- The Branches dropdown has a **Current Branch** option below **Show All**. It shows the history of whatever is checked out, and follows a checkout or a detached HEAD.
- The working tree changes open much faster when many files changed: the files show right away and their line counts follow, a long file list renders only the rows in view, and a refresh that changed nothing no longer redraws the details.
- The **Working tree changes** row is always shown, with how many files changed, e.g. "Working tree changes (3 files)". Its change actions show once there are changes.
- A divider separates the Graph and Actions column headers.
- Clipboard menu items say **Copy ... to Clipboard**, e.g. **Copy Branch Name to Clipboard**.

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
