# Technology transfer contracts in Vietnam — public materials

Public companion to the manuscript *Technology Transfer Across Regulatory Regimes: Relational Contracts and State Capacity in Vietnam* (Paper4L, V2).

Repository: [occbuu/paper-hd-cgcn](https://github.com/occbuu/paper-hd-cgcn)

The underlying news and journal `.docx` files are **not** included. They are third-party texts and remain in a separate private collection.

## Contents

| Path | What it is |
|---|---|
| [`paper/Paper4L_MsTam_V2.pdf`](paper/Paper4L_MsTam_V2.pdf) | Manuscript V2 |
| [`docs/04_Huong_dan_update_tung_buoc.md`](docs/04_Huong_dan_update_tung_buoc.md) | Seven stepwise inserts, V2 → V3 |
| [`scripts/run_robustness.py`](scripts/run_robustness.py) | K-scan, leave-one-out (Bùi 2019), news vs legal split, MDS |
| [`results/`](results/) | Tables and figures already produced (random seed 42) |

## Results at a glance

- Corpus inventory: 34 files — 27 news/policy, 7 legal-scholarly (`HDCG_*` + one journal file).
- K-scan (NMF, K = 3–8): silhouette is highest at K = 3 (0.243) and is 0.178 at K = 7. K = 7 is an interpretive choice, not a silhouette maximum.
- Leave-one-out: withholding Bùi Thị Hằng Nga (2019) keeps a contract/dispute topic; essential-facilities vocabulary does not return.
- News-only NMF: no contract-law topic.

Figures: [`results/fig_mds.png`](results/fig_mds.png), [`results/fig_k_scan.png`](results/fig_k_scan.png).

## Re-run (optional)

`results/` is sufficient for the paper appendix. To re-run you need a local folder of the 34 `.docx` files:

```bash
pip install scikit-learn pandas numpy matplotlib python-docx
set CORPUS_DIR=path\to\the\34\docx\files
python scripts/run_robustness.py
```

The first run may download a public Vietnamese wordlist and stopword list into `scripts/`. Those files are gitignored.
