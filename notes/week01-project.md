# Week 01 mini-project in git-daily-practice

Date - 23/11/2026

The Project - one feature, the way a team ships it

1. What I built
   1. Created `feat/about-page` and added `projects/week01/about.md` with 3 lines about me.
   2. Added `projects/week01/goals.md` on `feat/about-page` with my 3 goals for the 20 weeks.
   3. Pushed `feat/about-page`, opened a pull request on GitHub, reviewed `Files changed`, merged it, deleted the branch, and pulled into `main`.
   4. Linked both `about.md` and `goals.md` from `README.md` on `main`.

2. The commands I needed

   git switch -c feat/about-page
   git add . && git commit -m "feat(week01): add about page"
   git add . && git commit -m "feat(week01): add goals page"
   git push -u origin feat/about-page
   git switch main && git pull && git branch -d feat/about-page
   git add . && git commit -m "docs(week01): link the week 1 pages from the README"
   git push

3. What I would do differently next time
   1. Create and switch to the feature branch first before making any commits.
   2. Double-check that all files are saved in VS Code before staging and committing.
   3. Verify that commits are pushed to the feature branch before checking GitHub for the pull request banner.
