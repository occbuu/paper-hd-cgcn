# Paper4L public package

Standalone folder for a **new public** GitHub repository (to be created later).  
It is **not** part of the private `hopdong-CGCN` repo and has **no git remote** yet.

Do not copy `Dataset_Dinh_tinh/` here. Those `.docx` files are third-party texts and should stay private.

## Contents

| Path | What it is |
|---|---|
| `paper/Paper4L_MsTam_V2.pdf` | Manuscript V2 |
| `docs/04_Huong_dan_update_tung_buoc.md` | Seven stepwise inserts V2 → V3 |
| `scripts/run_robustness.py` | K-scan, leave-one-out, genre split, MDS |
| `results/` | Tables and figures already produced (seed 42) |

## When you create the public repo

On GitHub: **New repository** → Public → do not add a README (this folder already has one). Then, from this folder:

```bash
cd Paper4L_public
git init
git add .
git commit -m "Initial public replication package for Paper4L V2/V3."
git branch -M main
git remote add origin https://github.com/<your-user>/<your-public-repo>.git
git push -u origin main
```

Replace `<your-user>/<your-public-repo>` with the repo you create.

## Re-run (optional)

Precomputed files in `results/` are enough for the paper appendix. To re-run you need the 34 local `.docx` files:

```bash
pip install scikit-learn pandas numpy matplotlib python-docx
set CORPUS_DIR=D:\Support\MsTamHVPN\LuatKT\Paper4L\hopdong-CGCN\Dataset_Dinh_tinh
python scripts/run_robustness.py
```

The first run may download the public Vietnamese wordlist and stopword list into `scripts/`. Those downloads are gitignored.
