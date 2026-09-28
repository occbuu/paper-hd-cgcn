# Regulatory resilience in technology-transfer systems — public materials

Public companion to the manuscript *Regulatory Resilience in Technology Transfer Systems: Relational Contracting and State Capacity in Vietnam* (JTT submission version, 28 September 2026).

Repository: [occbuu/paper-hd-cgcn](https://github.com/occbuu/paper-hd-cgcn)

The underlying news and journal `.docx` files are **not** included. They are third-party texts and remain in a separate private collection.

## Current manuscript package

| Path | What it is |
|---|---|
| [`paper/JTT_Anonymous_Manuscript.pdf`](paper/JTT_Anonymous_Manuscript.pdf) | Latest anonymous manuscript prepared for *The Journal of Technology Transfer* |
| [`paper/JTT_Supplementary_Information.pdf`](paper/JTT_Supplementary_Information.pdf) | Supplementary methods, diagnostics and replication inventory |
| [`figures/`](figures/) | Separate high-resolution manuscript figures |
| [`scripts/run_robustness.py`](scripts/run_robustness.py) | K-scan, leave-one-out (Bùi 2019), genre split and MDS |
| [`results/`](results/) | Derived tables, assignments and figures (random seed 42) |

The earlier V2 manuscript and stepwise V2–V3 notes remain in `paper/` and `docs/` as version history.

## Results at a glance

- Corpus inventory: 34 files — 27 news/policy and 7 legal/professional documents.
- K-scan (NMF, K = 3–8): cosine silhouette is highest at K = 3 (0.243) and is 0.178 at K = 7. K = 7 is retained for interpretive coverage, not claimed as the statistical optimum.
- NMF–K-means agreement at K = 7 is ARI 0.499; the maximum in the reported scan is 0.836 at K = 5.
- Leave-one-out: withholding Bùi Thị Hằng Nga (2019) preserves a contract/dispute topic, while distinctive essential-facilities vocabulary does not recur.
- News/policy-only NMF does not produce a contract-law topic. The computational evidence therefore sets the agenda for doctrinal analysis; it does not estimate the population prevalence of transactional failure.

Figures: [`results/fig_mds.png`](results/fig_mds.png), [`results/fig_k_scan.png`](results/fig_k_scan.png).

## Re-run

The public outputs can be inspected directly. Exact re-estimation requires lawful local access to the 34 source `.docx` files and the preprocessing resources described in the Supplementary Information.

```bash
pip install scikit-learn pandas numpy matplotlib python-docx
set CORPUS_DIR=path\to\the\34\docx\files
python scripts/run_robustness.py
```

The first run may download a public Vietnamese wordlist and stopword list into `scripts/`; those files are gitignored.
