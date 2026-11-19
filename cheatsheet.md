# My Git Cheatsheet
Day 1 & Day 2 in git-daily-practice
Started: 18/11/2026 | Updated: 19/11/2026
Quick notes on the commands I actually used so I don't have to guess later.

Day 1 — Branches: a safe copy to try things

1. git switch -c lab/day001-branches                     - Creates a new branch named lab/day001-branches and switches to it right away (-c = create)
2. git branch                                            - Lists local branches; the * shows which branch I'm currently on
3. echo "Line written on a branch" > lab/day001.txt      - Creates lab/day001.txt with that line inside (or overwrites it if it's already there)
4. git add lab/day001.txt                                - Stages lab/day001.txt so it gets included in the next commit
5. git commit -m "feat(lab): add first file on a branch" - Saves the staged change to the branch history with that commit message
6. git switch main                                       - Switches back over to the main branch
7. ls lab                                                - Lists the files and folders inside the lab directory
8. git merge lab/day001-branches                         - Merges lab/day001-branches into the current branch (main), bringing those changes in
9. git branch -d lab/day001-branches                     - Deletes the local lab/day001-branches branch after it has been merged

Day 2 — Your first pull request

10. git pull                                             - Pulls the latest changes from the remote branch into my local branch
11. git switch -c lab/day002-pull-request                - Creates a fresh feature branch for the pull request workflow and switches to it
12. echo "My first pull request" > lab/day002.txt        - Creates lab/day002.txt with the starting text for the PR practice
13. git push -u origin lab/day002-pull-request           - Pushes the new local branch up to GitHub (origin) and sets upstream tracking (-u)
14. echo "Updated after my own review" >> lab/day002.txt   - Appends (>>) a new line to lab/day002.txt without wiping what's already there
15. git commit -am "feat(lab): update file after self review" - Stages tracked file changes and commits them in one step (-am)
16. git push                                             - Pushes new commits on the current tracked branch to GitHub (updating the open PR)
17. git switch main                                      - Switches back to main after merging the PR on GitHub
18. git branch -d lab/day002-pull-request                - Removes the local feature branch once its PR is merged into main
19. git fetch --prune                                    - Syncs remote-tracking refs and cleans up local references to branches already deleted on GitHub
20. echo "Merged through a pull request" >> lab/day002.txt - Appends a note to lab/day002.txt after pulling the merged changes into main
21. git log --oneline -8                                 - Shows the last 8 commits as compact single lines (hash + message)


