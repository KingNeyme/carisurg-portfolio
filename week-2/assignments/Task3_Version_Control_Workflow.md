# Task 3: Version Control Workflow

## Objective

Practise a real GitHub workflow:

1. Create a feature branch.
2. Make at least 3 meaningful commits.
3. Open a pull request to `main`.
4. Merge the pull request.
5. Screenshot the merged pull request and post it in Discord.

## Required Branch

Suggested branch name from the brief:

```text
feat/week-0-refactor
```

## Suggested Commit Plan

Use at least 3 meaningful commits, for example:

1. `Add repository structure and licence`
2. `Organise Week 0 notebooks and outputs`
3. `Document Week 2 setup workflow`

## Commands

```bash
git checkout -b feat/week-0-refactor
git add README.md LICENSE .gitignore requirements.txt notebooks docs data week-0 week-1 week-2 week-3
git commit -m "Add repository structure and licence"

git add week-0
git commit -m "Organise Week 0 portfolio submissions"

git add week-2 docs notebooks data
git commit -m "Document Week 2 project setup workflow"

git push -u origin feat/week-0-refactor
```

Then open GitHub, create a pull request into `main`, review it, merge it, and screenshot the merged PR.

## Discord Interim Submission

Post:

- GitHub repository link
- screenshot of merged pull request

## Status

- [ ] Feature branch created
- [ ] 3 commits made
- [ ] Pull request opened
- [ ] Pull request merged
- [ ] Screenshot shared in Discord
