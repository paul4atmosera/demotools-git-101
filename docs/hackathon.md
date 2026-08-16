# Day 1 hands-on lab

Work in a disposable sandbox repository. Replace `AB#1234` with a seeded Azure
Boards work-item ID when the GitHub/Azure Boards integration is available.

## 1. Branch, commit, and push

```bash
git checkout main
git pull --ff-only
git checkout -b feature/my-roadmap-note
```

Edit `docs/roadmap.md`, then inspect and share the change:

```bash
git status
git diff
git add docs/roadmap.md
git commit -m "Add my roadmap note (AB#1234)"
git push -u origin feature/my-roadmap-note
```

## 2. Pull request, review, and merge

Open a pull request to `main`. Add a short Markdown description, link the work
item, ask a partner to review it, squash-merge it, and delete the branch.

## 3. Create and resolve a conflict

Create two branches from the same `main` commit. On each branch, replace the
`Resolution choice` line in `docs/conflict-lab.md` with a different answer and
commit it. Merge the first branch, then update the second:

```bash
git fetch origin
git checkout <second-branch>
git merge origin/main
git status
```

Open `docs/conflict-lab.md`, keep the correct final text, and remove every
`<<<<<<<`, `=======`, and `>>>>>>>` marker. Then finish:

```bash
git add docs/conflict-lab.md
git commit -m "Resolve conflict-lab choice"
git push
```

To practice the escape hatch, start the conflicting merge again in a throwaway
branch and run `git merge --abort` before resolving it.

