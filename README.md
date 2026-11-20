# Decision Trees for AI Product Managers

Practise everything from the decision-tree lecture on a new case: **QuickCart**, a grocery delivery app that wants to predict which orders will arrive late. You fill in short blanks in prepared notebooks, run them cell by cell, and answer product questions. There are no functions to write and no long reading.

## Learning Objectives

By the end of this repository, you should be able to:

- Read a decision tree: root, question, branch, leaf, route, and explain a flagged prediction in one sentence.
- Explain how a tree chooses its questions (mixing score / Gini, "which question first", greedy growing).
- Recognise overfitting (train AUC 1.00) and control it with `max_depth` and `min_samples_leaf`; use `class_weight` when the rarer class (late) gets too little attention.
- Turn a score into an action with a threshold that fits business capacity.
- Spot data leakage and untrustworthy rules, compare a tree with logistic regression and KNN, and check results per group.
- Write a short ship / pilot / improve recommendation.

## Learning Path

Work through the notebooks in order. Each takes about 45–60 minutes.

| File / Folder | Description |
|---|---|
| [**1 - Your First Tree**](1_first_tree.ipynb) | Baseline, your own rule, mixing score, which question first, a depth-2 tree, leaf → score → threshold. |
| [**2 - Depth and Knobs**](2_depth_and_knobs.ipynb) | Train/test split, the perfect-training-score red flag, choosing depth with cross-validation, the three knobs, threshold as policy. |
| [**3 - PM Decisions**](3_pm_decisions.ipynb) | Find the leaky column, read rules (and distrust a 3-order rule), LR vs KNN vs tree, recall per group, prediction ≠ cause, your recommendation. |

### How the notebooks work

| Marker | Meaning |
|---|---|
| ▶️ **Run** | Just run the cell. |
| ✏️ **Your turn** | Replace every `___` with your answer, then run. |
| ✅ **Check** | Tells you if you got it right, with a hint if not. |
| 🧠 **Think** | A PM question: write 1–3 sentences in the answer cell below it. |

### Additional Folders and Files

| File / Folder | Description |
|---|---|
| [**Data**](data/) | `quickcart_orders.csv` (3,000 synthetic orders) and its data dictionary. |
| [**Solutions**](solutions/) | All three notebooks, solved, with outputs and sample answers. |
| [**pyproject.toml**](pyproject.toml) | Project configuration and dependencies. |
| [**uv.lock**](uv.lock) | Dependency lock file. |

## Setup

Use [uv](https://docs.astral.sh/uv/getting-started/installation/) 0.13.5 or newer and Python 3.13 (uv downloads it for you).

> [!NOTE]
> Text in angle brackets like `<repo-name>` is a **placeholder**. Replace it, including the `< >`.

### 1. Create the Repository from the Template

Click **Use this template** on GitHub, set yourself as the **Owner**, choose a name, disable **Include all branches**, and click **Create repository**.

### 2. Clone the Repository

```bash
git clone <copied-ssh-url>
```

### 3. Install the Dependencies

```bash
cd <repo-name>
uv sync
```

### 4. Open the Notebooks

```bash
code .
```

Open `1_first_tree.ipynb` and select the Python environment created by `uv sync` (`.venv`) as the kernel. Run the cells from top to bottom with `Shift + Enter`.

> [!TIP]
> If `uv sync` complains about the Python version, run `uv self update` and try again.

## References & Further Reading

- [scikit-learn: Decision Trees](https://scikit-learn.org/stable/modules/tree.html): how trees work, including `max_depth` and `min_samples_leaf`.
- [R2D3: A Visual Introduction to Machine Learning](http://www.r2d3.us/visual-intro-to-machine-learning-part-1/): an animated, beginner-friendly tour of how a tree grows.
- [scikit-learn: Cross-validation](https://scikit-learn.org/stable/modules/cross_validation.html): the "rehearsal exams" used in notebook 2.
