# dummy_rep_for_review
dummy repo for creating and trying out file. proper working files will be moved to the corresponding repo

# Folder structure for my understanding
  notes/          Your learning notes in Markdown
  notebooks/      Jupyter notebooks from course experiments
  src/            Reusable Python code
  experiments/    One-off experiments
  datasets/       Small sample datasets only, not large datasets
  models/         Avoid pushing big model files
  reports/        Summaries, findings, mini project reports
  assets/images/  Images used in README/reports
  scripts/        Utility scripts

# Everytime I start a new session
  cd ~/projects/deep-learning-learning-lab
  source .venv/bin/activate
  git pull
  code .

# Create files like
  notes/002_gradient_descent.md
  notebooks/002_gradient_descent_from_scratch.ipynb

# After finishing
  git status
  git add .
  git commit -m "Add gradient descent notes and experiment"
  git push

