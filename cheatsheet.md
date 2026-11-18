# My Git cheatsheet
First day in git-daily-practice
Date - 18/11/2025 
Creating cheatsheet for today practices - to notedown/trackdown what are the new commands I learned with a short explanation

CheatSheet

The Topic - Branches : A safe copy to try things 

The new codes I learned today :

1. git switch -c lab/day001-branches                     - Switched to a new branch 'lab/day001-branches'. -c means create

2. git branch                                            - Branches names. The * marks the branch you are on

3. echo "Line written on a branch" > lab/day001.txt      - Creates or overwrites lab/day001.txt with the text "Line written on a branch"

4. git add lab/day001.txt                                - Telling Git to include this file in next commit

5. git commit -m "feat(lab): add first file on a branch" - [lab/day001-branches 1a2b3c4] feat(lab): add first file on a branch

6. git switch main                                       - Switched to branch 'main'

7. ls lab                                                - It lists all files and folders inside lab directory

8. git merge lab/day001-branches                         - Merges the lab/day001-branches branch into current branch(usually main),combining all the changesmade on that branch

9. git branch -d lab/day001-branches                     - deletes the local branch lab/day001-branches because its changes have already been merged


