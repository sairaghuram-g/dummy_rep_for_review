# GitHub Markdown + LaTeX Handbook

This handbook is for writing clean `.md` files in GitHub repositories, especially for learning notes, README files, deep learning notes, Python commands, formulas, folder structures, and experiment documentation.

Use this as a reference whenever you edit `README.md` or files inside your `notes/` folder.

---

# 1. What is Markdown?

Markdown is a simple formatting language used by GitHub for files like:

```text
README.md
notes/001_pytorch_tensors.md
reports/experiment_results.md
```

Markdown is not like Microsoft Word.  
It does not preserve random spacing automatically.

To make text look clean, you need to use:

- Blank lines
- Headings
- Bullet points
- Code blocks
- Tables
- Inline code
- LaTeX math blocks

---

# 2. Basic README Structure

A good README usually follows this structure:

```markdown
# Repo Name

Short description of the repo.

---

## Goal

Explain what this repo is for.

---

## Folder Structure

Explain folders using a table.

---

## Setup

Mention installation steps.

---

## Daily Workflow

Mention the commands you normally run.

---

## Learning Progress

Use checklist or bullet points.

---

## Rules

Mention what not to push.
```

Example:

```markdown
# deep-learning-learning-lab

This repository contains my deep learning notes, PyTorch implementations, experiments, and computer vision practice projects.

---

## Goal

Build strong practical and theoretical understanding of deep learning for computer vision, ADAS, and autonomous driving applications.

---

## Folder Structure

| Folder | Purpose |
|---|---|
| `notes/` | Learning notes |
| `notebooks/` | Jupyter notebooks |
| `src/` | Reusable Python code |
| `experiments/` | One-off experiments |
| `reports/` | Mini reports and findings |

---

## Daily Workflow

```bash
git pull
source .venv/bin/activate
code .
```

After finishing:

```bash
git status
git add .
git commit -m "Meaningful commit message"
git push
```
```

---

# 3. Headings

Use `#` symbols for headings.

```markdown
# Main Title

## Big Section

### Subsection

#### Smaller subsection

##### Very small subsection
```

Rules:

- Use only one `#` main title at the top.
- Use `##` for main sections.
- Use `###` for subsections.
- Leave a blank line before and after headings.

Good:

```markdown
## Setup

Run the following commands.
```

Bad:

```markdown
## Setup
Run the following commands.
```

The bad one may still work, but it is less clean.

---

# 4. Paragraphs and New Lines

Markdown merges normal lines into one paragraph unless you separate them properly.

Bad:

```markdown
This is line one.
This is line two.
This is line three.
```

This may render as:

```text
This is line one. This is line two. This is line three.
```

Good method 1: use blank lines.

```markdown
This is line one.

This is line two.

This is line three.
```

Good method 2: use bullets.

```markdown
- This is line one.
- This is line two.
- This is line three.
```

Good method 3: force a line break using two spaces at the end of each line.

```markdown
This is line one.  
This is line two.  
This is line three.
```

Practical advice: use blank lines or bullets. Avoid relying on two trailing spaces because they are invisible and easy to miss.

---

# 5. Bullet Points

Use `-` for bullet points.

```markdown
- Learn the concept
- Write notes
- Implement code
- Run experiment
- Write observations
- Push to GitHub
```

Nested bullets:

```markdown
- Deep Learning
  - Tensors
  - Autograd
  - Gradient descent
- Computer Vision
  - CNN
  - Object detection
  - Segmentation
```

Rules:

- Use two spaces before nested bullets.
- Keep bullet points short.
- Do not write very long paragraphs as bullets unless needed.

---

# 6. Numbered Lists

Use numbered lists for step-by-step procedures.

```markdown
1. Create the repo.
2. Clone the repo.
3. Open it in VS Code.
4. Create files.
5. Commit changes.
6. Push to GitHub.
```

Nested numbered list:

```markdown
1. Setup Git.
   1. Configure name.
   2. Configure email.
   3. Setup SSH key.
2. Setup Python.
   1. Create virtual environment.
   2. Install packages.
   3. Save `requirements.txt`.
```

---

# 7. Inline Code

Use single backticks for commands, filenames, folders, variables, package names, and short code.

```markdown
Use `git status` to check current changes.

Create notes inside `notes/`.

The file name should be `001_pytorch_tensors.md`.

The variable `learning_rate` controls the update step size.
```

Use inline code for:

```text
git status
README.md
notes/
learning_rate
torch.Tensor
requirements.txt
```

Do not use inline code for long commands. Use code blocks instead.

---

# 8. Code Blocks

Use triple backticks for code blocks.

## 8.1 Bash / Terminal Commands

Use `bash` for terminal commands.

````markdown
```bash
git status
git add .
git commit -m "Update README"
git push
```
````

Rendered:

```bash
git status
git add .
git commit -m "Update README"
git push
```

## 8.2 Python Code

Use `python` for Python code.

````markdown
```python
import torch

x = torch.tensor([1, 2, 3])
print(x.shape)
```
````

Rendered:

```python
import torch

x = torch.tensor([1, 2, 3])
print(x.shape)
```

## 8.3 Plain Text

Use `text` for outputs, folder structures, and general non-code content.

````markdown
```text
notes/
notebooks/
src/
experiments/
reports/
```
````

Rendered:

```text
notes/
notebooks/
src/
experiments/
reports/
```

## 8.4 JSON

Use `json` for JSON content.

````markdown
```json
{
  "learning_rate": 0.001,
  "batch_size": 32,
  "epochs": 10
}
```
````

## 8.5 YAML

Use `yaml` for YAML config files.

````markdown
```yaml
learning_rate: 0.001
batch_size: 32
epochs: 10
```
````

## 8.6 `.gitignore`

Use `gitignore` for `.gitignore` content.

````markdown
```gitignore
.venv/
__pycache__/
*.pt
*.pth
datasets/raw/
```
````

---

# 9. Terminal Commands vs Python Code

Do not mix terminal commands and Python code.

Bad:

````markdown
```python
pip install torch
python train.py
```
````

Why bad?  
`pip install torch` and `python train.py` are terminal commands, not Python code.

Good:

````markdown
```bash
pip install torch
python train.py
```
````

Python code should look like this:

````markdown
```python
import torch

print(torch.__version__)
```
````

---

# 10. Command Output

Use `text` for command outputs.

Example:

````markdown
```bash
python train.py
```

Output:

```text
Epoch 1/10 - loss: 0.8234 - accuracy: 0.6421
Epoch 2/10 - loss: 0.6123 - accuracy: 0.7345
```
````

For training logs, do not use `python`; use `text`.

---

# 11. Tables

Tables are useful for folder structures, experiment results, and comparisons.

## 11.1 Basic Table

```markdown
| Folder | Purpose |
|---|---|
| `notes/` | Learning notes |
| `notebooks/` | Jupyter notebooks |
| `src/` | Reusable Python code |
| `reports/` | Experiment summaries |
```

Rendered:

| Folder | Purpose |
|---|---|
| `notes/` | Learning notes |
| `notebooks/` | Jupyter notebooks |
| `src/` | Reusable Python code |
| `reports/` | Experiment summaries |

## 11.2 Experiment Result Table

```markdown
| Learning Rate | Result | Observation |
|---|---|---|
| `0.001` | Slow convergence | Stable but too slow |
| `0.01` | Good convergence | Best result |
| `0.1` | Unstable | Loss fluctuated |
| `1.0` | Diverged | Too large |
```

Rendered:

| Learning Rate | Result | Observation |
|---|---|---|
| `0.001` | Slow convergence | Stable but too slow |
| `0.01` | Good convergence | Best result |
| `0.1` | Unstable | Loss fluctuated |
| `1.0` | Diverged | Too large |

Rules:

- Every table needs a header row.
- Every table needs a separator row: `|---|---|`
- Use backticks for code-like values.
- Keep table cells short.

---

# 12. Horizontal Lines

Use three hyphens:

```markdown
---
```

Example:

```markdown
# My Repo

Short description.

---

## Setup
```

Use horizontal lines to separate large sections, not every small paragraph.

---

# 13. Bold and Italic

## Bold

```markdown
**Important:** Always run `git pull` before editing.
```

Rendered:

**Important:** Always run `git pull` before editing.

## Italic

```markdown
*Optional:* Use branches later when your workflow becomes stable.
```

Rendered:

*Optional:* Use branches later when your workflow becomes stable.

## Bold + Italic

```markdown
***Very important:*** Do not push passwords.
```

Rendered:

***Very important:*** Do not push passwords.

---

# 14. Checkboxes / Task Lists

Useful for learning progress.

```markdown
## Learning Progress

- [x] Create GitHub repo
- [x] Push README
- [ ] Create virtual environment
- [ ] Add first notebook
- [ ] Push first experiment
```

Rendered:

- [x] Create GitHub repo
- [x] Push README
- [ ] Create virtual environment
- [ ] Add first notebook
- [ ] Push first experiment

---

# 15. Links

Use this format:

```markdown
[Text to show](https://example.com)
```

Examples:

```markdown
[GitHub](https://github.com)

[PyTorch Documentation](https://pytorch.org/docs/stable/index.html)

[Python Documentation](https://docs.python.org/3/)
```

Do not paste long raw URLs unless necessary. They make README files ugly.

---

# 16. Images

Use this format:

```markdown
![Image description](assets/images/image_name.png)
```

Example:

```markdown
![Training loss curve](assets/images/loss_curve.png)
```

Rules:

- Keep images inside `assets/images/`.
- Use meaningful image names.
- Use relative paths.
- Do not push very large images.

Good image names:

```text
loss_curve_lr_comparison.png
cnn_architecture.png
confusion_matrix_mnist.png
```

Bad image names:

```text
image1.png
screenshot.png
finalfinal.png
```

---

# 17. Folder Trees

Use a `text` code block.

````markdown
```text
deep-learning-learning-lab/
├── README.md
├── requirements.txt
├── notes/
│   ├── 001_pytorch_tensors.md
│   └── 002_autograd.md
├── notebooks/
│   ├── 001_pytorch_tensors.ipynb
│   └── 002_autograd_experiment.ipynb
├── src/
├── experiments/
├── reports/
└── assets/
    └── images/
```
````

Rendered:

```text
deep-learning-learning-lab/
├── README.md
├── requirements.txt
├── notes/
│   ├── 001_pytorch_tensors.md
│   └── 002_autograd.md
├── notebooks/
│   ├── 001_pytorch_tensors.ipynb
│   └── 002_autograd_experiment.ipynb
├── src/
├── experiments/
├── reports/
└── assets/
    └── images/
```

Do not write folder trees as normal paragraphs.

Bad:

```markdown
notes/ learning notes notebooks/ jupyter notebooks src/ python files
```

Good:

````markdown
```text
notes/       Learning notes
notebooks/   Jupyter notebooks
src/         Python files
```
````

---

# 18. GitHub Callouts

GitHub supports useful note boxes.

```markdown
> [!NOTE]
> This repo is for learning and experiments.

> [!TIP]
> Commit after every meaningful experiment.

> [!WARNING]
> Do not push large datasets, model weights, passwords, or API keys.

> [!IMPORTANT]
> Always run `git pull` before editing from another machine.

> [!CAUTION]
> Commands like `git reset --hard` can delete local changes.
```

Use them sparingly. Too many warnings make the README noisy.

---

# 19. Escaping Special Characters

Some characters have special meaning in Markdown:

```text
#  heading
-  bullet
*  italic/bold
`  inline code/code block
|  table separator
[ ] links
( ) links
$  math
```

If you want to show them literally, use backslash or code formatting.

Example:

```markdown
Use `#` for headings.

Use `-` for bullets.

Use `|` inside tables carefully.
```

If you need to escape:

```markdown
\# This will not become a heading
```

---

# 20. Comments in Markdown

Markdown supports HTML comments.

```markdown
<!-- This is a comment. It will not be visible in the rendered README. -->
```

Use this for reminders:

```markdown
<!-- TODO: Add result image after running experiment -->
```

---

# 21. LaTeX in GitHub Markdown

GitHub supports LaTeX-style math in Markdown using:

- `$...$` for inline math
- `$$...$$` for block math

Use LaTeX mainly for formulas, not for normal text.

---

# 22. Inline LaTeX Math

Use single dollar signs for equations inside sentences.

```markdown
The learning rate is represented as $\alpha$.
```

```markdown
The prediction error is $y - \hat{y}$.
```

```markdown
The weight update depends on $\frac{\partial L}{\partial w}$.
```

Rules:

- Use inline math for short formulas.
- Keep inline formulas small.
- Do not put long equations inside a sentence.

---

# 23. Block LaTeX Math

Use double dollar signs for important formulas.

```markdown
$$
MSE = \frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y}_i)^2
$$
```

Good formatting:

```markdown
The mean squared error is:

$$
MSE = \frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y}_i)^2
$$

This penalizes larger errors more strongly.
```

Bad formatting:

```markdown
The mean squared error is:
$$
MSE = \frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y}_i)^2
$$
This penalizes larger errors more strongly.
```

Always keep a blank line before and after block equations.

---

# 24. Common LaTeX Symbols for Deep Learning

| Meaning | LaTeX | Renders as |
|---|---|---|
| Alpha | `$\alpha$` | $\alpha$ |
| Beta | `$\beta$` | $\beta$ |
| Theta | `$\theta$` | $\theta$ |
| Lambda | `$\lambda$` | $\lambda$ |
| Mu | `$\mu$` | $\mu$ |
| Sigma | `$\sigma$` | $\sigma$ |
| Epsilon | `$\epsilon$` | $\epsilon$ |
| Delta | `$\Delta$` | $\Delta$ |
| Partial derivative | `$\partial$` | $\partial$ |
| Infinity | `$\infty$` | $\infty$ |

---

# 25. Subscripts and Superscripts

## Subscript

```markdown
$x_i$
```

Use braces for multiple characters:

```markdown
$x_{train}$
```

## Superscript

```markdown
$x^2$
```

Use braces for multiple characters:

```markdown
$x^{(i)}$
```

## Combined

```markdown
$x_i^2$
```

```markdown
$x_{train}^{(i)}$
```

Deep learning examples:

```markdown
The input sample is $x^{(i)}$.

The true label is $y_i$.

The predicted label is $\hat{y}_i$.
```

---

# 26. Hats, Bars, and Bold Symbols

## Predicted value

```markdown
$\hat{y}$
```

## Mean

```markdown
$\bar{x}$
```

## Vector

```markdown
$\mathbf{x}$
```

## Matrix

```markdown
$\mathbf{W}$
```

Examples:

```markdown
The predicted output is $\hat{y}$.

The input vector is $\mathbf{x}$.

The weight matrix is $\mathbf{W}$.
```

---

# 27. Fractions

Basic fraction:

```markdown
$\frac{a}{b}$
```

Accuracy formula:

```markdown
$$
accuracy = \frac{\text{correct predictions}}{\text{total predictions}}
$$
```

Loss average:

```markdown
$$
L = \frac{1}{n}\sum_{i=1}^{n}L_i
$$
```

---

# 28. Summation

Basic summation:

```markdown
$$
\sum_{i=1}^{n} x_i
$$
```

Mean:

```markdown
$$
\mu = \frac{1}{n}\sum_{i=1}^{n}x_i
$$
```

Mean squared error:

```markdown
$$
MSE = \frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y}_i)^2
$$
```

Cross entropy:

```markdown
$$
L = -\sum_{i=1}^{C} y_i \log(\hat{y}_i)
$$
```

---

# 29. Derivatives and Partial Derivatives

Normal derivative:

```markdown
$$
\frac{dL}{dw}
$$
```

Partial derivative:

```markdown
$$
\frac{\partial L}{\partial w}
$$
```

Gradient descent update:

```markdown
$$
w_{new} = w_{old} - \alpha \frac{\partial L}{\partial w}
$$
```

Chain rule:

```markdown
$$
\frac{\partial L}{\partial w}
=
\frac{\partial L}{\partial \hat{y}}
\cdot
\frac{\partial \hat{y}}{\partial w}
$$
```

---

# 30. Matrices and Vectors

## Column Vector

```markdown
$$
\mathbf{x} =
\begin{bmatrix}
x_1 \\
x_2 \\
x_3
\end{bmatrix}
$$
```

## Matrix

```markdown
$$
\mathbf{W} =
\begin{bmatrix}
w_{11} & w_{12} \\
w_{21} & w_{22}
\end{bmatrix}
$$
```

## Matrix Multiplication

```markdown
$$
\mathbf{z} = \mathbf{W}\mathbf{x} + \mathbf{b}
$$
```

## Neural Network Layer

```markdown
$$
\mathbf{h} = \sigma(\mathbf{W}\mathbf{x} + \mathbf{b})
$$
```

---

# 31. Piecewise Functions

Useful for ReLU.

```markdown
$$
ReLU(x) =
\begin{cases}
x, & x > 0 \\
0, & x \leq 0
\end{cases}
$$
```

Leaky ReLU:

```markdown
$$
LeakyReLU(x) =
\begin{cases}
x, & x > 0 \\
0.01x, & x \leq 0
\end{cases}
$$
```

---

# 32. Multi-line Equations

Use `aligned`.

```markdown
$$
\begin{aligned}
z &= wx + b \\
\hat{y} &= \sigma(z) \\
L &= -y\log(\hat{y})
\end{aligned}
$$
```

This is useful for showing forward pass steps.

Another example:

```markdown
$$
\begin{aligned}
\mathbf{z}^{[1]} &= \mathbf{W}^{[1]}\mathbf{x} + \mathbf{b}^{[1]} \\
\mathbf{a}^{[1]} &= ReLU(\mathbf{z}^{[1]}) \\
\mathbf{z}^{[2]} &= \mathbf{W}^{[2]}\mathbf{a}^{[1]} + \mathbf{b}^{[2]} \\
\hat{y} &= softmax(\mathbf{z}^{[2]})
\end{aligned}
$$
```

---

# 33. Common Deep Learning Formulas

## Linear Model

```markdown
$$
\hat{y} = wx + b
$$
```

## Linear Layer

```markdown
$$
\mathbf{z} = \mathbf{W}\mathbf{x} + \mathbf{b}
$$
```

## Sigmoid

```markdown
$$
\sigma(x) = \frac{1}{1 + e^{-x}}
$$
```

## ReLU

```markdown
$$
ReLU(x) = \max(0, x)
$$
```

## Softmax

```markdown
$$
softmax(z_i) = \frac{e^{z_i}}{\sum_{j=1}^{K}e^{z_j}}
$$
```

## Binary Cross Entropy

```markdown
$$
BCE = -[y\log(\hat{y}) + (1-y)\log(1-\hat{y})]
$$
```

## Multi-class Cross Entropy

```markdown
$$
L = -\sum_{i=1}^{C} y_i \log(\hat{y}_i)
$$
```

## Mean Squared Error

```markdown
$$
MSE = \frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y}_i)^2
$$
```

## L2 Regularization

```markdown
$$
L_{total} = L_{data} + \lambda \sum_{i}w_i^2
$$
```

## Gradient Descent

```markdown
$$
\theta_{new} = \theta_{old} - \alpha \nabla_{\theta}L
$$
```

---

# 34. LaTeX Text Inside Equations

Normal words inside math should use `\text{}`.

Bad:

```markdown
$$
accuracy = correct predictions / total predictions
$$
```

Good:

```markdown
$$
accuracy = \frac{\text{correct predictions}}{\text{total predictions}}
$$
```

Another example:

```markdown
$$
Loss = \text{classification loss} + \text{regularization penalty}
$$
```

---

# 35. Common LaTeX Mistakes

## Mistake 1: Python syntax inside LaTeX

Bad:

```markdown
$$
y_hat = 1 / (1 + exp(-x))
$$
```

Good:

```markdown
$$
\hat{y} = \frac{1}{1 + e^{-x}}
$$
```

## Mistake 2: Missing braces

Bad:

```markdown
$x_train$
```

This renders as `x` with only `t` as subscript, then `rain`.

Good:

```markdown
$x_{train}$
```

## Mistake 3: Block equations without blank lines

Bad:

```markdown
Formula:
$$
y = wx + b
$$
Next paragraph.
```

Good:

```markdown
Formula:

$$
y = wx + b
$$

Next paragraph.
```

## Mistake 4: Using LaTeX for everything

Bad idea:

```markdown
$$
This repo contains my notes
$$
```

Use normal Markdown for normal text. Use LaTeX only for formulas.

---

# 36. Learning Note Template

Use this template for every concept note.

```markdown
# Topic Name

## What I Learned

- Point 1
- Point 2
- Point 3

---

## Intuition

Explain the concept in simple words.

---

## Formula

$$
formula_here
$$

Where:

- $x$ means input
- $y$ means actual output
- $\hat{y}$ means predicted output

---

## Code Practiced

```python
# Python code here
```

---

## Experiment

I changed:

- Learning rate
- Batch size
- Number of layers

---

## Result

| Change | Result | Observation |
|---|---|---|
| `learning_rate = 0.001` | Slow | Stable but slow |
| `learning_rate = 0.01` | Good | Best result |
| `learning_rate = 0.1` | Unstable | Loss jumped |

---

## Mistakes I Made

- Mistake 1
- Mistake 2

---

## Final Understanding

Write your final understanding in your own words.
```

---

# 37. Gradient Descent Note Example

```markdown
# Gradient Descent

## What I Learned

- Gradient descent is used to reduce loss.
- It updates model parameters step by step.
- The learning rate controls the step size.

---

## Intuition

If the model prediction is wrong, the loss becomes high.

Gradient descent checks the slope of the loss and updates the weights in the direction that reduces the loss.

---

## Formula

$$
w_{new} = w_{old} - \alpha \frac{\partial L}{\partial w}
$$

Where:

- $w_{new}$ is the updated weight
- $w_{old}$ is the current weight
- $\alpha$ is the learning rate
- $L$ is the loss
- $\frac{\partial L}{\partial w}$ is the gradient

---

## Code Practiced

```python
w = w - learning_rate * gradient
```

---

## Experiment

I tried different learning rates.

| Learning Rate | Result | Observation |
|---|---|---|
| `0.001` | Very slow | Stable but slow |
| `0.01` | Good | Smooth convergence |
| `0.1` | Unstable | Loss fluctuated |
| `1.0` | Diverged | Step size too large |

---

## Final Understanding

Gradient descent is not magic. It is repeated correction based on the direction of the error.
```

---

# 38. Experiment Report Template

Use this inside `reports/`.

```markdown
# Experiment Name

## Objective

What was the goal of this experiment?

---

## Hypothesis

What did I expect before running the experiment?

---

## Setup

| Item | Value |
|---|---|
| Dataset | MNIST |
| Model | Simple MLP |
| Optimizer | Adam |
| Loss | Cross entropy |
| Epochs | 10 |
| Batch size | 32 |

---

## Commands Used

```bash
python train.py --epochs 10 --batch-size 32 --lr 0.001
```

---

## Results

| Metric | Value |
|---|---|
| Training accuracy | 98.2% |
| Validation accuracy | 96.4% |
| Training loss | 0.052 |
| Validation loss | 0.121 |

---

## Observations

- Training accuracy was higher than validation accuracy.
- Small gap means overfitting was not severe.
- Validation loss stopped improving after epoch 8.

---

## Conclusion

The model learned the dataset reasonably well. Next step is to test regularization or a CNN baseline.
```

---

# 39. README Template for Deep Learning Repo

```markdown
# Deep Learning Learning Lab

This repository contains my deep learning notes, PyTorch implementations, experiments, and computer vision practice projects.

---

## Goal

Build strong practical and theoretical understanding of deep learning for computer vision, ADAS, and autonomous driving applications.

---

## Folder Structure

| Folder | Purpose |
|---|---|
| `notes/` | Concept notes in Markdown |
| `notebooks/` | Jupyter notebooks and experiments |
| `src/` | Reusable Python modules |
| `experiments/` | Small experiments and comparisons |
| `datasets/` | Small sample datasets only |
| `models/` | Avoid pushing large model files |
| `reports/` | Mini reports and findings |
| `assets/images/` | Images used in README/reports |
| `scripts/` | Utility scripts |

---

## Setup

```bash
cd ~/projects/deep-learning-learning-lab
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

---

## Daily Workflow

Start every session:

```bash
cd ~/projects/deep-learning-learning-lab
source .venv/bin/activate
git pull
code .
```

After finishing:

```bash
git status
git add .
git commit -m "Meaningful commit message"
git push
```

---

## Learning Progress

- [ ] PyTorch tensors
- [ ] Autograd
- [ ] Gradient descent
- [ ] Loss functions
- [ ] Optimizers
- [ ] Overfitting and regularization
- [ ] CNN basics
- [ ] Autoencoders
- [ ] GAN basics
- [ ] Object detection
- [ ] Monocular distance estimation

---

## Rules

> [!WARNING]
> Do not push large datasets, model weights, passwords, API keys, or company-related confidential files.

> [!TIP]
> Every topic should include notes, code, experiment result, and observations.
```

---

# 40. Git Workflow Section for README

```markdown
## Git Workflow

Before starting work:

```bash
git pull
```

After making changes:

```bash
git status
git add .
git commit -m "Describe what changed"
git push
```

Check commit history:

```bash
git log --oneline
```

Check current branch:

```bash
git branch
```

Check remote URL:

```bash
git remote -v
```
```

---

# 41. Good Commit Messages

Good:

```text
Add tensor basics notebook
Add autograd notes and experiment
Implement gradient descent from scratch
Compare SGD and Adam optimizers
Add CNN baseline for MNIST
Fix tensor shape issue in CNN notebook
Update README with setup instructions
```

Bad:

```text
update
changes
done
final
test
asdf
new
```

Rule: the commit message should clearly say what changed.

---

# 42. `.gitignore` Template for Deep Learning Repos

Use this in `.gitignore`.

```gitignore
# Python
__pycache__/
*.py[cod]
*.pyo
*.pyd
.Python

# Virtual environments
.venv/
venv/
env/

# Jupyter
.ipynb_checkpoints/

# VS Code
.vscode/

# Data
datasets/raw/
datasets/large/
*.csv
*.xlsx
*.parquet
*.h5
*.pkl

# Models
models/*.pt
models/*.pth
models/*.onnx
models/*.ckpt
models/*.safetensors

# Logs
logs/
runs/
wandb/
mlruns/

# Environment files and secrets
.env
*.env
secrets/
config/secrets.yaml

# OS files
.DS_Store
Thumbs.db
```

Be careful: this ignores all `.csv` files. If you want to push a tiny sample CSV, put it somewhere like:

```text
datasets/sample/
```

and modify `.gitignore` accordingly.

---

# 43. Common README Mistakes

## Mistake 1: Writing folder structure as paragraph

Bad:

```markdown
notes/ learning notes notebooks/ jupyter notebooks src/ python code reports/ summaries
```

Good:

```markdown
| Folder | Purpose |
|---|---|
| `notes/` | Learning notes |
| `notebooks/` | Jupyter notebooks |
| `src/` | Python code |
| `reports/` | Summaries |
```

## Mistake 2: Writing commands as normal text

Bad:

```markdown
git status git add . git commit -m "message" git push
```

Good:

````markdown
```bash
git status
git add .
git commit -m "message"
git push
```
````

## Mistake 3: No blank line before code block

Bad:

````markdown
Run this:
```bash
git status
```
````

Good:

````markdown
Run this:

```bash
git status
```
````

## Mistake 4: Using backslash before commands

Bad:

```markdown
\ git status
```

Good:

````markdown
```bash
git status
```
````

---

# 44. VS Code Markdown Preview

In VS Code:

1. Open `.md` file.
2. Press:

```text
Ctrl + Shift + V
```

This opens Markdown preview.

Alternative:

1. Right-click inside the Markdown file.
2. Click **Open Preview**.

Useful extensions:

```text
Markdown All in One
Markdown Preview Enhanced
```

But remember: GitHub rendering is the final check.

---

# 45. Practical Workflow for Editing README

Before editing:

```bash
git pull
```

Open VS Code:

```bash
code .
```

Edit `README.md`.

Preview:

```text
Ctrl + Shift + V
```

Check Git status:

```bash
git status
```

Commit and push:

```bash
git add README.md
git commit -m "Update README formatting"
git push
```

Refresh GitHub page.

---

# 46. What to Put in a Learning Note

A useful note is not just copied theory. It should have:

- What the concept means
- Why it matters
- Formula
- Simple intuition
- Code example
- Experiment result
- Mistakes
- Final understanding

Bad note:

```markdown
# Gradient Descent

Gradient descent is an optimization algorithm.
```

Better note:

```markdown
# Gradient Descent

## What it means

Gradient descent updates model weights to reduce loss.

## Formula

$$
w_{new} = w_{old} - \alpha \frac{\partial L}{\partial w}
$$

## Intuition

The gradient tells the direction of increase in loss.  
So we move in the opposite direction.

## Experiment

I changed learning rate from `0.001` to `1.0`.

## Observation

- `0.001` was slow.
- `0.01` was stable.
- `1.0` diverged.

## Final Understanding

Learning rate controls how big each correction step is.
```

---

# 47. Your Best Habit

For every learning topic, create two files:

```text
notes/003_gradient_descent.md
notebooks/003_gradient_descent_from_scratch.ipynb
```

Then commit:

```bash
git add .
git commit -m "Add gradient descent notes and experiment"
git push
```

This creates a real public learning trail.

---

# 48. Quick Cheat Sheet

```markdown
# Title

## Section

### Subsection

Normal paragraph.

- Bullet item
- Bullet item
  - Nested bullet

1. Step one
2. Step two

`inline code`

```bash
terminal command
```

```python
python code
```

```text
plain output or folder tree
```

| Column 1 | Column 2 |
|---|---|
| Value 1 | Value 2 |

> [!WARNING]
> Important warning here.

[Link text](https://example.com)

![Image description](assets/images/image.png)

Inline math: $\alpha = 0.001$

Block math:

$$
L = -\sum_{i=1}^{C} y_i \log(\hat{y}_i)
$$
```

Important: the cheat sheet above contains code fences inside a code fence. When copying into your own file, copy the individual parts carefully.

---

# 49. Final Rules

Use this rule set:

1. Use `#`, `##`, `###` for headings.
2. Use blank lines between sections.
3. Use bullets for lists.
4. Use tables for structured comparisons.
5. Use `bash` code blocks for terminal commands.
6. Use `python` code blocks for Python code.
7. Use `text` code blocks for outputs and folder trees.
8. Use `$...$` for inline math.
9. Use `$$...$$` for block math.
10. Use LaTeX only for formulas, not normal text.
11. Preview before pushing.
12. Commit only meaningful changes.
13. Never push passwords, API keys, company files, huge datasets, or model weights.

---

# 50. One-Minute README Quality Check

Before pushing, ask:

- Does the README have clear headings?
- Are commands inside code blocks?
- Are folder structures in tables or text blocks?
- Are formulas rendered properly?
- Are there blank lines around code blocks and equations?
- Did I avoid pushing sensitive files?
- Did I preview it in VS Code?
- Does it look clean on GitHub?

If yes, commit and push.

```bash
git status
git add .
git commit -m "Update markdown notes"
git push
```
