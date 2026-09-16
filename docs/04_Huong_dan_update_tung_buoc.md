# Cập nhật V2 → V3 (từng bước)

Làm **một lần một mục**, lưu bản, rồi mới sang mục tiếp.  
Không làm Lần 7 (cắt từ) cho đến khi Lần 1–6 đã vào bài.

**Gói public (hình, bảng, script):** [github.com/occbuu/paper-hd-cgcn](https://github.com/occbuu/paper-hd-cgcn)

| Cần dùng | Đường dẫn |
|---|---|
| MDS | [`results/fig_mds.png`](https://github.com/occbuu/paper-hd-cgcn/blob/main/results/fig_mds.png) |
| Quét K | [`results/fig_k_scan.png`](https://github.com/occbuu/paper-hd-cgcn/blob/main/results/fig_k_scan.png) |
| Bảng số | [`results/k_scan.csv`](https://github.com/occbuu/paper-hd-cgcn/blob/main/results/k_scan.csv) |
| Bản thảo V2 | [`paper/Paper4L_MsTam_V2.pdf`](https://github.com/occbuu/paper-hd-cgcn/blob/main/paper/Paper4L_MsTam_V2.pdf) |

Bản local cùng nội dung: `Paper4L_public/`. Không dùng corpus private `hopdong-CGCN/Dataset_Dinh_tinh/` trong bài hay trên GitHub public.

---

## Lần 1 — Sửa số corpus (Mục 3.2, đoạn mở)

**Tìm:** twenty-six items of news and policy reporting … eight scholarly

**Thay bằng:**

The corpus comprises thirty-four Vietnamese-language documents on technology transfer, science, technology and innovation. By filename, twenty-seven are news or policy reports from government portals and the press, and seven are legal or professional publications (six items with the HDCG prefix and one journal file). Bùi Thị Hằng Nga (2019) is document HDCG_A09. Each file is treated as one document.

**Xong khi:** trong bài không còn cụm 26/8.

---

## Lần 2 — Chèn hình MDS (Mục 3.2, sau Bảng 2 / bốn chiều)

**Chèn ngay sau đoạn:** The percentages state the relative concentration of this corpus…

**Đoạn chèn:**

Figure 3 plots the thirty-four documents in two-dimensional MDS of TF-IDF cosine distances, coloured by the K = 7 assignment (random seed 42). Theme 1 forms a dense cloud — the only grouping large enough to be called a centre of gravity. Theme 6 lies apart from that cloud, consistent with a genre effect rather than with a claim that essential-facilities doctrine sits at the core of public discussion. Theme 5 is split and Theme 2 is dispersed. The geometry is a check on interpretation, not an independent proof of the four dimensions.

**Caption:** Figure 3. MDS of the 34 documents in TF-IDF space, coloured by NMF topic (K = 7). Source: [github.com/occbuu/paper-hd-cgcn](https://github.com/occbuu/paper-hd-cgcn) (`results/fig_mds.png`).

**File hình:** `results/fig_mds.png`

**Xong khi:** có Figure 3 MDS trong Mục 3.2.

---

## Lần 3 — Chèn bảng quét K (Mục 3.2, đoạn chọn K = 7)

**Tìm đoạn đang viết:** Seven topics were fixed for interpretation, rather than established as a unique statistical optimum. The reported Adjusted Rand Index…

**Giữ** câu ARI(NMF, LDA) = 0.448 tại K = 7 so với 0.060 tại K = 3.

**Thêm ngay sau câu đó:**

Seven was not selected by maximising a single internal index. Appendix Table A1 reports a scan of K = 3 to 8 on the full corpus. Cosine silhouette is highest at K = 3 (0.243) and declines to 0.178 at K = 7; the share of the largest topic falls from 55.9 per cent to 38.2 per cent over the same range. Agreement between NMF and K-means on the same TF-IDF matrix is highest at K = 5 (ARI = 0.836) and is moderate at K = 7 (0.499). These figures confirm that silhouette on a small corpus favours a coarse partition. K = 7 is retained because it yields interpretable legal and policy problems and because the four-dimension aggregation used for doctrinal questions is recovered from it. It is not claimed to be the unique statistical optimum.

**Bảng A1 (đặt Appendix; trong bài chính chỉ dẫn “Table A1”):**

| K | Silhouette | Largest topic share (%) | ARI (NMF, K-means) |
|---|---|---|---|
| 3 | 0.243 | 55.9 | 0.614 |
| 4 | 0.225 | 52.9 | 0.586 |
| 5 | 0.209 | 44.1 | 0.836 |
| 6 | 0.183 | 38.2 | 0.510 |
| 7 (retained) | 0.178 | 38.2 | 0.499 |
| 8 | 0.185 | 38.2 | 0.740 |

**Caption bảng:** Table A1. Topic-number scan on the 34-document corpus. Silhouette uses cosine distance. K = 7 is an interpretive choice, not the silhouette maximum. Source: `results/k_scan.csv`.

**Hình phụ (Appendix):** `results/fig_k_scan.png`  
Caption: Figure A1. Silhouette and ARI across K = 3–8.

**Xong khi:** bài nói rõ K = 7 không phải tối ưu silhouette.

---

## Lần 4 — Thay câu “tests proposed, not completed” (cuối Mục 3.2)

**Tìm và xóa hết câu:**

A leave-one-source-out analysis and comparisons within genres would test whether the grouping survives removal of its most doctrinally distinctive source. Those tests are proposed, not reported as completed.

**Thay bằng hai đoạn sau (giữ nguyên đoạn LDA không gom Theme 6 ở ngay trước đó):**

Two robustness checks were completed on the same specification. Assignments and keywords are in the public replication repository ([github.com/occbuu/paper-hd-cgcn](https://github.com/occbuu/paper-hd-cgcn), folder `results/`).

First, Bùi Thị Hằng Nga (2019) — the dual-role source in Theme 6 — was withheld and NMF was re-estimated at K = 7 on the remaining thirty-three documents. A contract-and-dispute topic survived (keywords: contract, technology transfer, law, right, dispute). The two remaining Theme 6 items, Hồ Minh Khánh (2024) and the practitioner note, were assigned to that topic, together with one news item on FDI transfer practice. The distinctive essential-facilities vocabulary (essential, ownership, doctrine) did not reappear. Theme 6 therefore cannot be treated as a computational discovery of the essential-facilities doctrine. It can be treated as a small lexical neighbourhood in which transfer contracts and disputes are discussed, and that neighbourhood does not collapse when the dual-role source is removed.

Second, NMF was re-estimated at K = 7 on the twenty-seven news and policy documents alone. No contract-law or essential-facilities topic appeared. The news-only partition recovers general transfer activity, industrial AI and data, agriculture, semiconductors, university innovation, and strategic-technology or cybersecurity vocabulary. The legal questions about acceptance, restrictive terms and contractual defaults are therefore carried by the legal-scholarly subset, not by the public discourse at large. Theme 6 is agenda-setting material for doctrinal analysis, not evidence that those contractual problems dominate Vietnamese technology discussion.

**Xong khi:** trong bài không còn chữ “proposed, not reported as completed”.

---

## Lần 5 — Sửa đoạn giới hạn ở Mục 9 (Conclusion)

**Tìm đoạn:** The limitations remain substantial. Thirty-four published documents cannot establish…

**Thay cụm nói về Theme 6** (câu bắt đầu “In particular, Theme 6 is a small grouping…”) **bằng:**

In particular, Theme 6 is a three-document grouping. Withholding Bùi Thị Hằng Nga (2019) preserves a contract-and-dispute neighbourhood but not the essential-facilities vocabulary; a news-only partition does not recover that neighbourhood at all. The legal questions in Dimension 1 about acceptance and restrictive terms are therefore questions the legal literature puts to the statute, not questions shown to dominate public discussion.

**Giữ nguyên** các câu sau đó về contracts/judgments và cut-off 16 September 2026.  
**Xóa hoặc sửa** câu “Additional references do not cure the incomplete replication materials…” — gói tái lập công khai đã có trên GitHub; chỉ còn thiếu toàn văn `.docx` (bản quyền), không phải thiếu bảng/hình/script.

**Xong khi:** Kết luận khớp với Lần 4 (đã chạy test) và Lần 6 (có repo public).

---

## Lần 6 — Data availability (trước References)

**Chèn heading mới** ngay trước `References`:

**Data availability**

Replication materials are available at [https://github.com/occbuu/paper-hd-cgcn](https://github.com/occbuu/paper-hd-cgcn). The repository contains: (i) a document inventory of the thirty-four files, with identifiers, filenames and a genre flag; (ii) the robustness script, including TF-IDF settings (minimum document frequency 2, maximum document frequency 0.9), NMF initialisation (nndsvda) and random seed 42; (iii) document–topic assignments at K = 7; (iv) topic-keyword tables for the full corpus, the leave-one-out run, and the news-only partition; and (v) the files needed to redraw Figure 3 and Table A1 (`results/fig_mds.png`, `results/fig_k_scan.png`, `results/k_scan.csv`). The repository does not include copyrighted full texts of the underlying news or journal articles; those remain in the authors’ research files and can be inspected for verification subject to the original publishers’ terms.

**Không** dẫn `hopdong-CGCN` (repo private) và **không** yêu cầu zip thủ công: link GitHub là nguồn nộp kèm.

**Xong khi:** có mục Data availability trỏ đúng repo public.

---

## Lần 7 — Cắt từ (chỉ sau khi Lần 1–6 xong)

V2 khoảng 12.200 từ. Mục tiêu phần chính: 8.500–9.500 từ.  
**Không cắt:** vai kép Bùi (2019); leave-one-out; news-only; NĐ 101/2026; Luật AI; Chương bán dẫn Luật 71/2025; link GitHub.

### Nếu nộp IIC hoặc Law, Innovation and Technology

Giữ Mục 4.3, 5.2–5.3, Bảng 3, TTBER, Điều 144 Luật SHTT, Luật Cạnh tranh.

Cắt hoặc chuyển appendix: tokenisation chi tiết; disclaimer lặp (giữ một khối ở 3.1); nông nghiệp còn một đoạn; CHIPS/EU Chips Act còn 4–5 câu; Figure 4.

Câu contribution (thay đoạn đóng góp ở Mục 2):

The article’s legal contribution is a scoped map of Vietnamese technology-transfer protection after the 2025–2026 reforms: industrial-property and competition rules overlap more than a registration-plus-dominance story implies, yet technology-specific defaults for acceptance and improvements to unregistered know-how remain unspecified, and digital transfers require coordination among transfer, data and AI statutes rather than a single ownership rule.

### Nếu nộp Journal of Technology Transfer hoặc Science and Public Policy

Giữ Figure 1, Figure 4, Mục 8.1–8.2.

Chuyển appendix: 14 mục Điều 23; chi tiết phạt vi phạm; từng nhánh Điều 144(2); từng điều Data Act/AI Act. Bảng 3 còn 8–10 hàng.

Câu contribution:

The article proposes a dual-function account of the technology-transfer contract — as a performance arrangement between firms and as a compliance protocol with public authorities — and specifies a time-limited inter-agency pilot, with indicators that separate processing activity from operating capability, through which that account can be tested.

---

## Thứ tự không được đảo

1. Số corpus  
2. MDS  
3. Bảng K  
4. Hai kiểm tra độ vững  
5. Kết luận  
6. Data availability  
7. Cắt theo tạp chí  

Lần 2 và 3 có thể đổi chỗ cho nhau. Lần 4 phải trước Lần 5. Lần 7 luôn cuối.
