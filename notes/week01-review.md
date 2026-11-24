Week 01 review in git-daily-practice
Date - 24/11/2026

The Week - Branches and pull requests

1. Week summary
   1. Day 001 - Branches: a safe copy to try things - I can spin up a branch to experiment freely, switch back and forth without losing work, and clean up merged branches so `main` stays tidy.
   2. Day 002 - Your first pull request - I can push a branch to GitHub, open a Pull Request, review diffs, and merge changes cleanly instead of throwing everything straight onto `main`.
   3. Day 003 - Merge commits and the history graph - I can read how branches connect in the commit graph and tell when Git fast-forwards versus when it creates a merge commit.

2. Self-check answers (no notes first, then check and correct)
   1. What does the _ in git branch mean? Why did lab/day001.txt disappear when you switched to main?
      -> The `_`shows the branch I am currently standing on (where`HEAD`points). When I switched back to`main`, `lab/day001.txt`seemed to vanish because it belonged to a commit on my feature branch and wasn't part of`main`'s snapshot yet.
   2. Why did the pull request show 2 commits after your second push, without you opening a new one?
      -> Because a Pull Request watches the branch itself rather than freezing the commits from when I opened it—pushing another commit to that branch pulls the new commit into the PR automatically.
   3. When does Git make a merge commit and when does it fast-forward?
      -> Git fast-forwards when `main` hasn't moved ahead since the branch split off, so it just slides the branch pointer forward along a straight line. It creates a merge commit when both branches have moved forward separately and need a new commit to tie those two histories together.

3. Mistakes and fixes
   1. Mistake - Committed straight onto `main` out of habit instead of making a branch first | Fix - Saved that commit onto a new branch with `git branch <name>`, stepped `main` back using `git reset --hard HEAD~1`, and jumped over with `git switch <name>`.
   2. Mistake - Ran `git push` on a new branch before linking it to `origin` | Fix - Followed Git's hint and ran `git push --set-upstream origin <branch>` (or `-u`) so future pushes and pulls know where that branch lives.
   3. Mistake - Tried to delete a branch while I was still standing on it | Fix - Moved off it first with `git switch main`, then cleaned it up safely with `git branch -d <branch>`.

4. Plan for week 02 - Conflicts and the stash
   1. Handle merge conflicts calmly in VS Code—reading both sides carefully so I keep the right logic from each branch instead of panicking or wiping out changes by accident.
   2. Get comfortable using `git stash`, `git stash list`, and `git stash pop` whenever I need to jump to another branch halfway through editing a file.
