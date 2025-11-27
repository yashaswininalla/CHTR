<!-- .github/copilot-instructions.md -->
# Copilot / AI agent instructions — CHTR (ECG Arrhythmia Analysis)

Purpose
- Help maintainers and AI coding agents quickly understand and extend the analysis notebooks in this repository.

Repository shape & big picture
- This repo contains exploratory Jupyter notebooks that analyze ECG datasets. Primary notebooks at the repo root:
  - `Copy_of_AFDB.ipynb` — Atrial Fibrillation (AFDB) analysis
  - `Copy_of_SVDB.ipynb` — Supraventricular (SVDB) analysis
  - `Copy_of_CNE_(1) (1).ipynb` — Additional ECG analysis (CNE)
- There is no package/module layout, CI, or test suite present; notebooks are the main deliverable.

Agent guidance (practical)
- Edit notebooks conservatively: prefer small, focused PRs that reference the notebook filename in the title and description.
- When refactoring notebook code into scripts, create a `scripts/` folder (e.g., `scripts/preprocess_afdb.py`) and add a short usage docstring.
- If you add dependencies, include a `requirements.txt` at the repo root and update `README.md` with exact install commands.
- Clear notebook outputs before committing. Recommended tools: `jupyter nbconvert --clear-output` or `nbstripout`.

Data and external integrations
- Notebooks reference PhysioNet datasets; raw data files are not included here. Do not pull or add entire datasets without asking the repo owner.
- Use the `wfdb` library to access PhysioNet records if needed. Example usage is present in notebooks' first cells.

Environment & common commands
- Recommended: Python 3.8+ + virtual environment. PowerShell quick-start:
```
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install jupyter numpy pandas matplotlib seaborn scikit-learn wfdb
```
- Run notebooks: `jupyter notebook` or `jupyter lab` and open the files above.
- Convert repeatable notebook workflows into scripts using `jupyter nbconvert --to script notebook.ipynb` then refine the script.

When to ask the user / maintainers
- Confirm before downloading or committing large datasets (PhysioNet) or running long training jobs.
- Ask for a preferred environment pinning (exact package versions) if you are preparing reproducible runs.

Examples of safe tasks for AI agents
- Add docstrings and clarifying comments to top cells of `Copy_of_AFDB.ipynb` describing expected local dataset layout.
- Create `requirements.txt` listing libraries used in notebooks and update `README.md` with install/run steps.
- Extract the preprocessing block from `Copy_of_AFDB.ipynb` into `scripts/preprocess_afdb.py` with CLI flags for `--record-id` and `--out-dir`.

Files to reference
- `Copy_of_AFDB.ipynb`, `Copy_of_SVDB.ipynb`, `Copy_of_CNE_(1) (1).ipynb` — primary working files.
- `README.md` — update this file when runtime/developer steps change.

If uncertain about scope
- Open a draft PR with questions in the description and mention the repo owner for approval before major changes (data downloads, large model training, or adding heavy dependencies).
