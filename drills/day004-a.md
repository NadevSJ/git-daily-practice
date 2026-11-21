Day 001 from memory - Branches: a safe copy to try things
Date - 20/11/2026

1. The commands I remember, in order (no looking)
   1. git status
   2. git switch -c feature/day001
   3. git branch
   4. echo "day 001 practice" > lab/day001.txt
   5. git add lab/day001.txt
   6. git commit -m "feat(lab): add day 001 branch practice"
   7. git switch main
   8. git status

2. After checking with Day 001 in the Hub

   Missed - git push -u origin feature/day001 (if pushing the new branch to remote)
   Wrong - Used git branch instead of git switch -c to create and switch -> right version: git switch -c feature/day001
   Why it matters - Branches isolate experimental work so main stays clean and safe until changes are ready.
