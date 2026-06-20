# dummy_rep_for_review

Dummy repo for creating and trying out files. Proper working files will be moved to the corresponding repo.

---

## Folder structure for my understanding

| Folder | Purpose |
|---|---|
| `notes/` | Learning notes in Markdown |
| `notebooks/` | Jupyter notebooks from course experiments |
| `src/` | Reusable Python code |
| `experiments/` | One-off experiments |
| `datasets/` | Small sample datasets only, not large datasets |
| `models/` | Avoid pushing big model files |
| `reports/` | Summaries, findings, mini project reports |
| `assets/images/` | Images used in README/reports |
| `scripts/` | Utility scripts |

---

## Every time I start a new session

```bash
cd ~/projects/dummy_rep_for_review
source .venv/bin/activate
git pull
code .
```

## create files like this
notes/002_gradient_descent.md
notebooks/002_gradient_descent_from_scratch.ipynb

## After fininshing

```bash
git status
git add .
git commit -m "Add gradient descent notes and experiment"
git push
```

