Week 01 review in git-daily-practice
Date - 24/11/2026

The Week - Branches and pull requests

1. Week summary
   1. Day 001 - Branches: a safe copy to try things - I can spin up a branch to experiment freely, switch back and forth without losing work, and clean up merged branches so `main` stays tidy.
   2. Day 002 - Your first pull request - I can push a branch to GitHub, open a Pull Request, review diffs, and merge changes cleanly instead of throwing everything straight onto `main`.
   3. Day 003 - Merge commits and the history graph - I can read how branches connect in the commit graph and tell when Git fast-forwards versus when it creates a merge commit.

2. Self-check answers (no notes first, then check and correct)
   1. What does the _ in git branch mean? Why did lab/day001.txt disappear when you switched to main?
      -> The `_`shows which branch I am currently standing on (where`HEAD`points). When I switched back to`main`, `lab/day001.txt`seemed to vanish because it lived inside a commit on my feature branch and wasn't part of`main`'s snapshot yet.
   2. Why did the pull request show 2 commits after your second push, without you opening a new one?
      -> Because a Pull Request follows the branch itself, not a frozen list of commits from the moment I opened it—pushing another commit to that branch updates the PR automatically.
   3. When does Git make a merge commit and when does it fast-forward?
      -> Git fast-forwards when `main` hasn't moved ahead since the branch started, so it just slides the branch pointer forward in a straight line. It makes a merge commit when both branches have moved on separately and need to be joined together.

3. Mistakes and fixes
   1. Mistake - Committed work straight onto `main` out of habit | Fix - Saved the commit onto a new branch with `git branch feature-fix`, moved `main` back with `git reset --hard HEAD~1`, and switched over using `git switch feature-fix`.
   2. Mistake - Ran `git push` on a brand-new branch before setting upstream tracking | Fix - Linked local and remote with `git push -u origin <branch-name>` so plain `git push` and `git pull` work smoothly from then on.
   3. Mistake - Tried to delete a branch while I was still checked out on it | Fix - Moved back with `git switch main` first, then safely removed the merged branch with `git branch -d <branch-name>`.

4. Plan for week 02 - Conflicts and the stash
   1. Handle merge conflicts calmly in VS Code—reading both sides carefully and checking the final file before committing instead of guessing.
   2. Build real muscle memory with `git stash`, `git stash list`, and `git stash pop` whenever I need to switch branches mid-change.
