# CHTR — ECG Arrhythmia Analysis

This repository contains exploratory Jupyter notebooks for ECG arrhythmia analysis and experiments. The notebooks included are copies of analyses on publicly available ECG databases (e.g., AFDB, SVDB). Use the notebooks to reproduce visualizations, preprocessing steps, feature extraction, and model experiments.

**Note:** These are analysis notebooks (research/experimental). Review dataset licensing and the notebooks' top cells for dataset download instructions before running.
# CHTR — ECG Arrhythmia Analysis

Short description
- Notebooks demonstrate preprocessing, visualization, and modeling experiments performed on public ECG databases .

Primary notebooks
- `AFDB.ipynb` — Atrial Fibrillation database (AFDB) analysis and preprocessing examples.
- `SVDB.ipynb` — Supraventricular database (SVDB) analysis.
- `MIT-BIH.ipynb` — Additional ECG analysis (CNE).

Quick start (PowerShell)

1) Create and activate a virtual environment

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

2) Install recommended packages

```powershell
python -m pip install --upgrade pip
pip install jupyter numpy pandas matplotlib seaborn scikit-learn wfdb
```

3) Run Jupyter and open the notebooks

```powershell
jupyter notebook
# or
jupyter lab
```

Notes about data
- The repository does not include the ECG datasets. Notebooks reference PhysioNet datasets (see the notebooks' top cells). Typical usage is to download records locally or use the `wfdb` library to access PhysioNet data.
- Recommended local layout when adding small sample data: create a `data/` folder and update notebook paths to point to `data/`.

Recommended developer workflow
- Keep notebook outputs cleared before committing (use `jupyter nbconvert --clear-output` or `nbstripout`).
- If you convert notebook logic into reusable code, place scripts under `scripts/` and add `requirements.txt` to pin dependencies.
- Make small, focused PRs that reference the notebook filename in the title.

Reproducibility & environment
- Python 3.8+ recommended. Pin exact package versions if you need reproducible runs (create `requirements.txt`).

Acknowledgements
- Notebooks were developed using PhysioNet datasets. Follow PhysioNet's licensing and citation requirements when using those datasets.
pip install -r requirements.txt

```



If you don't have `requirements.txt` yet, install common packages directly:

