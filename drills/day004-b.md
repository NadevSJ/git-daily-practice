Day 002 from memory - Your first pull request
Date - 20/11/2026

1. The commands I remember, in order (no looking)
   1. git status
   2. git switch -c pr/day002-note
   3. echo "day 002 pr test" > lab/day002.txt
   4. git add lab/day002.txt
   5. git commit -m "feat(lab): add day 002 pr note"
   6. git push -u origin pr/day002-note
   7. git switch main
   8. git pull

2. After checking with Day 002 in the Hub

   Missed - checking the PR status / merging or cleaning up the branch after review if part of that lesson
   Wrong - tried to do a PR straight from main instead of pushing a feature branch first -> right version: create/switch to a branch, commit, push -u origin <branch>, then open the PR against main
   Why it matters - Pull requests track branch changes automatically on GitHub, so pushing another commit to the same branch updates the open PR without opening a new one.
