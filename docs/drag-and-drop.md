# Drag and drop in the graph

Drag a branch label or commits onto another row of the graph to rebase, merge or cherry-pick. Resting on a target previews the result in the graph; dropping opens a menu of what the drop can do, and the usual prompt confirms before anything changes.

| Drag | Onto | Does |
|---|---|---|
| A branch label | Another commit or branch | Rebase the branch there, even one that isn't checked out |
| A branch label | The checked-out branch | Rebase or merge |
| A remote-tracking branch | The checked-out branch | Merge |
| Commits, or a selection | The checked-out branch | Cherry-pick |

The commits a drop moves are banded in their lane's color, first where they are, then where the preview puts them. With your system's reduce motion setting on, the graph changes without animating.

## Rebase a branch

Drag a branch label onto another branch. Resting there previews the branch's commits copied on top of it, the menu previews each action as you point at it, and Rebase runs it.

![A branch label dragged onto main, previewing the rebase before it runs](https://raw.githubusercontent.com/ZacheryGlass/sidereal/main/media/drag/rebase-branch.gif)

## Rebase the checked-out branch

Drag the checked-out branch onto another branch to rebase it there. Escape puts everything back.

![The checked-out branch dragged onto another branch, previewed, then put back with Escape](https://raw.githubusercontent.com/ZacheryGlass/sidereal/main/media/drag/rebase-checked-out.gif)

## Fast-forward a branch

A branch that's behind has no commits of its own to copy, so only its label moves.

![A branch that's behind dragged onto main, only its label moving](https://raw.githubusercontent.com/ZacheryGlass/sidereal/main/media/drag/fast-forward.gif)

## Merge into the checked-out branch

Drop a branch on the checked-out branch and choose Merge. The preview shows the merge commit before it's made.

![A branch dropped on the checked-out branch, previewing the merge commit](https://raw.githubusercontent.com/ZacheryGlass/sidereal/main/media/drag/merge-branch.gif)

## Merge a remote-tracking branch

A remote-tracking branch dropped on the checked-out branch can only be merged.

![A remote-tracking branch dropped on the checked-out branch, previewing the merge](https://raw.githubusercontent.com/ZacheryGlass/sidereal/main/media/drag/merge-remote.gif)

## Cherry-pick a commit

Drag a commit onto the checked-out branch. The preview puts a copy on top, and Cherry Pick makes it.

![A commit dragged onto the checked-out branch, previewing its copy on top](https://raw.githubusercontent.com/ZacheryGlass/sidereal/main/media/drag/cherry-pick.gif)

## Cherry-pick several commits

Select commits with Ctrl/Cmd+Click or Shift+Click, then drag them. They're copied oldest first.

![Two selected commits dragged onto the checked-out branch, copied oldest first](https://raw.githubusercontent.com/ZacheryGlass/sidereal/main/media/drag/cherry-pick-selection.gif)

## Change your mind

Move to another target and the preview follows. Escape puts everything back, and the label returns where it came from.

![A branch label moved between drop targets, then put back with Escape](https://raw.githubusercontent.com/ZacheryGlass/sidereal/main/media/drag/change-target.gif)
