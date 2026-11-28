# My Git Cheatsheet

Day 1 – Day 9 in `git-daily-practice`  
Started: 18/11/2026 | Updated: 25/11/2026  
Quick notes on the commands I actually used so I don't have to guess later.

---

## Day 1 — Branches: a safe copy to try things

1. `git switch -c lab/day001-branches` - Creates a new branch named `lab/day001-branches` and switches to it right away (`-c` = create)
2. `git branch` - Lists local branches; the `*` shows which branch I'm currently on
3. `echo "Line written on a branch" > lab/day001.txt` - Creates `lab/day001.txt` with that line inside (or overwrites it if it's already there)
4. `git add lab/day001.txt` - Stages `lab/day001.txt` so it gets included in the next commit
5. `git commit -m "feat(lab): add first file on a branch"` - Saves the staged change to the branch history with that commit message
6. `git switch main` - Switches back over to the `main` branch
7. `ls lab` - Lists the files and folders inside the `lab` directory
8. `git merge lab/day001-branches` - Merges `lab/day001-branches` into the current branch (`main`), bringing those changes in
9. `git branch -d lab/day001-branches` - Deletes the local `lab/day001-branches` branch after it has been merged

---

## Day 2 — Your first pull request

10. `git pull` - Pulls the latest changes from the remote branch into my local branch
11. `git switch -c lab/day002-pull-request` - Creates a fresh feature branch for the pull request workflow and switches to it
12. `echo "My first pull request" > lab/day002.txt` - Creates `lab/day002.txt` with the starting text for the PR practice
13. `git push -u origin lab/day002-pull-request` - Pushes the new local branch up to GitHub (`origin`) and sets upstream tracking (`-u`)
14. `echo "Updated after my own review" >> lab/day002.txt` - Appends (`>>`) a new line to `lab/day002.txt` without wiping what's already there
15. `git commit -am "feat(lab): update file after self review"` - Stages tracked file changes and commits them in one step (`-am`)
16. `git push` - Pushes new commits on the current tracked branch to GitHub (updating the open PR)
17. `git switch main` - Switches back to `main` after merging the PR on GitHub
18. `git branch -d lab/day002-pull-request` - Removes the local feature branch once its PR is merged into `main`
19. `git fetch --prune` - Syncs remote-tracking refs and cleans up local references to branches already deleted on GitHub
20. `echo "Merged through a pull request" >> lab/day002.txt` - Appends a note to `lab/day002.txt` after pulling the merged changes into `main`
21. `git log --oneline -8` - Shows the last 8 commits as compact single lines (hash + message)

---

## Day 3 — Merge commits and the history graph

22. `git switch -c lab/day003-merge` - Creates the branch `lab/day003-merge` (`-c` = create) from the commit you are on, and moves you onto it
23. `echo "feature work" > lab/day003-feature.txt` - Writes `"feature work"` into `lab/day003-feature.txt` (`>` creates the file, or replaces what it had)
24. `git add lab/day003-feature.txt` - Puts the current version of `lab/day003-feature.txt` into the staging area, the box for your next commit
25. `git commit -m "feat(lab): add feature file for merge practice"` - Saves what is staged as a commit with the message `"feat(lab): add feature file for merge practice"`
26. `git switch main` - Moves you onto the `main` branch
27. `git merge lab/day003-merge --no-edit` - Brings the commits of the branch `lab/day003-merge` into the branch you are on
28. `git log --oneline --graph -6` - Shows the history: one line per commit (short ID and message), branch lines drawn on the left, showing where branches split and join, only the latest 6 commits
29. `git branch -d lab/day003-merge` - Deletes the branch name `lab/day003-merge` on your laptop

---

## Week 01 project — one feature, the way a team ships it

30. `git add .` - Stages every new, changed or deleted file in this folder and the folders below it
31. `git commit -m "feat(week01): add about page"` - Saves what is staged as a commit with the message `"feat(week01): add about page"`
32. `git push -u origin feat/about-page` - Uploads the branch `feat/about-page` and its commits to GitHub (`origin` is the name of your GitHub copy)
33. `git switch main` - Moves you onto the `main` branch
34. `git pull` - Downloads new commits from GitHub and adds them to your current branch
35. `git branch -d feat/about-page` - Deletes the branch name `feat/about-page` on your laptop
36. `git push` - Uploads your local commits on the current branch to GitHub

---

## Day 6 — Week 1 review: Branches and pull requests

37. `cd ~/projects/git-daily-practice && git pull` - Moves into the `git-daily-practice` repository and pulls the latest remote changes before starting
38. `mkdir -p notes && code notes/week01-review.md` - Creates the `notes` folder if needed (`-p`) and opens `notes/week01-review.md` in VS Code
39. `git add notes/week01-review.md && git commit -m "docs(review): week 01 summary"` - Stages and commits the Week 1 summary in `notes/week01-review.md`
40. `git add notes/week01-review.md && git commit -m "docs(review): answer the week 01 self-check questions"` - Stages and commits the memory-recall answers to the self-check questions
41. `code cheatsheet.md` - Opens `cheatsheet.md` in VS Code so Week 1 commands can be grouped cleanly without duplicates
42. `git add cheatsheet.md && git commit -m "docs(cheatsheet): tidy week 01 commands"` - Stages and commits the cleaned-up cheatsheet
43. `git add notes/week01-review.md && git commit -m "docs(review): week 01 mistakes and fixes"` - Stages and commits the logged mistakes and fixes for Week 1
44. `git add notes/week01-review.md && git commit -m "docs(review): plan week 02"` - Stages and commits the Week 2 goals covering merge conflicts and `git stash`
45. `echo "- Day 006: week 1 review" >> log.md && git add log.md && git commit -m "chore(log): complete day 006"` - Appends today's completion line to `log.md`, stages it, and commits it
46. `git push` - Pushes all local commits on the current branch up to GitHub so today's contribution shows on your profile graph

---

## Day 7 — Create a merge conflict and solve it

47. `echo "color = blue" > lab/day007.txt` - Writes `"color = blue"` into `lab/day007.txt` (`>` creates the file, or replaces what it had)
48. `git add lab/day007.txt` - Puts the current version of `lab/day007.txt` into the staging area, the box for your next commit
49. `git commit -m "feat(lab): add settings file for conflict practice"` - Saves what is staged as a commit with the message `"feat(lab): add settings file for conflict practice"`
50. `git switch -c lab/day007-conflict` - Creates the branch `lab/day007-conflict` (`-c` = create) from the commit you are on, and moves you onto it
51. `git commit -am "feat(lab): change color to green on the branch"` - Stages every changed tracked file and commits it in one step (`-am`) with the message `"feat(lab): change color to green on the branch"`
52. `git switch main` - Moves you onto the `main` branch
53. `git merge lab/day007-conflict` - Brings the commits of the branch `lab/day007-conflict` into the branch you are on (pausing with a conflict when both sides edit the same line)
54. `git status` - Tells you which branch you are on and lists files in three groups: staged (green, will go into the next commit), changed but not staged (red) and untracked (new files Git does not know yet)
55. `cat lab/day007.txt` - Prints the whole content of `lab/day007.txt` in the terminal
56. `git log --oneline --graph -5` - Shows the history: one line per commit (short ID and message), branch lines drawn on the left, showing where branches split and join, only the latest 5 commits
57. `git branch -d lab/day007-conflict` - Deletes the branch name `lab/day007-conflict` on your laptop

---

## Day 8 — Cancel a merge, or take one side

58. `echo "size = small" > lab/day008.txt` - Writes `"size = small"` into `lab/day008.txt` (`>` creates the file if missing or overwrites existing content)
59. `git add lab/day008.txt` - Puts the current version of `lab/day008.txt` into the staging area, the box for your next commit
60. `git commit -m "feat(lab): add size setting"` - Saves what is staged as a commit with the message `"feat(lab): add size setting"`
61. `git switch -c lab/day008-sides` - Creates the branch `lab/day008-sides` (`-c` = create) from the commit you are on, and moves you onto it
62. `git commit -am "feat(lab): set size to large on the branch"` - Stages every changed tracked file and commits it in one step (`-am`) with the message `"feat(lab): set size to large on the branch"`
63. `git switch main` - Moves you onto the `main` branch
64. `git merge lab/day008-sides` - Brings the commits of the branch `lab/day008-sides` into the branch you are on (stopping on conflict when both branches modified `lab/day008.txt`)
65. `git merge --abort` - Stops a merge that hit a conflict and puts everything back the way it was before the merge
66. `git status` - Tells you which branch you are on and lists files in three groups: staged (green, will go into the next commit), changed but not staged (red) and untracked (new files Git does not know yet)
67. `git restore --theirs lab/day008.txt` - Fills `lab/day008.txt` with the version from the branch you are bringing in (`--theirs`), dropping your side of the conflict
68. `cat lab/day008.txt` - Prints the whole content of `lab/day008.txt` in the terminal
69. `git branch -d lab/day008-sides` - Deletes the branch name `lab/day008-sides` on your laptop

---

## Day 9 — Stash: put unfinished work in a drawer

70. `cd ~/projects/git-daily-practice && git pull` - Moves into the `git-daily-practice` repository and pulls the latest remote changes before starting
71. `echo "draft line 1" > lab/day009.txt && git add lab/day009.txt && git commit -m "feat(lab): start a draft file"` - Creates `lab/day009.txt` with `"draft line 1"`, stages it, and saves the initial draft commit
72. `echo "half-finished idea" >> lab/day009.txt` - Appends (`>>`) `"half-finished idea"` to `lab/day009.txt` without committing it
73. `git status` - Shows the current branch and lists modified tracked files not yet staged
74. `git stash` - Saves uncommitted changes on tracked files onto the stash stack and cleans the working directory back to `HEAD`
75. `git status` - Confirms the working tree is clean after stashing
76. `cat lab/day009.txt` - Prints `lab/day009.txt` showing only `"draft line 1"` while the half-finished line is stashed away
77. `echo "urgent fix" > lab/day009-urgent.txt && git add lab/day009-urgent.txt && git commit -m "fix(lab): add the urgent fix first"` - Creates, stages, and commits the urgent fix file cleanly on its own
78. `git stash list` - Lists saved stashes on the stack, with the newest entry at `stash@{0}`
79. `git stash pop` - Applies the newest stash (`stash@{0}`) back to the working directory and drops it from the stash stack
80. `git commit -am "feat(lab): finish the idea from the stash"` - Stages tracked file modifications and commits the completed draft change in one step (`-am`)
81. `mkdir -p notes && code notes/day009.md` - Creates the `notes` directory if missing (`-p`) and opens `notes/day009.md` in VS Code
82. `git add notes/day009.md && git commit -m "docs(notes): day 009 - Stash"` - Stages and commits today's reflection notes
83. `code cheatsheet.md` - Opens `cheatsheet.md` in VS Code to record Day 9 commands
84. `git add cheatsheet.md && git commit -m "docs(cheatsheet): add day 009 commands"` - Stages and commits the updated cheatsheet
85. `echo "- Day 009: Stash" >> log.md && git add log.md && git commit -m "chore(log): complete day 009"` - Appends Day 9 to `log.md`, stages it, and commits the log entry
86. `git push` - Pushes all local commits on the branch to GitHub so the contribution graph updates
