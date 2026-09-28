# Retail teaching extract

**Source:** Chen, D. (2015). *Online Retail*. UCI Machine Learning Repository. [Dataset](https://archive.ics.uci.edu/dataset/352/online+retail), [DOI](https://doi.org/10.24432/C5BW33). Licensed by UCI under [Creative Commons Attribution 4.0](https://creativecommons.org/licenses/by/4.0/).

**Adaptation:** the course authors selected customer/invoice records and converted the spreadsheet to compressed CSV. The source dataset contains 541,909 invoice lines. The supplied extract contains **44,324 rows**, 400 non-null customer IDs, and 130 sampled anonymous invoices. Dates run from 2010-12-01 to 2011-12-09. No artificial defects were inserted; no cleaning was applied during extraction. Synthetic tables inside the notebooks are explicitly separate teaching examples.

## Reproduction and integrity

`retail_manifest.json` records the source URL, source ZIP checksum, extract checksum, random seed (42), and selection rule. The development repository's `scripts/prepare_retail.py` recreates the adaptation using the locked environment. Each notebook validates the supplied compressed file's checksum before reading it. Keep the original supplied file; perform experimental changes in DataFrame copies.

Selection: sort the unique known customer IDs, uniformly sample 400 without replacement, and retain all their source rows. Separately sample ten distinct anonymous invoice IDs in each calendar month, retaining their anonymous rows. Restore source row order. Customers selected this way retain their complete **observed source-window** history, not their lifetime history.

## Field guide

| Field | Meaning and caution |
|---|---|
| InvoiceNo | Invoice identifier; prefix `C` denotes cancellation. Repeats across product lines. |
| StockCode | Product identifier; treat as a string. Non-product codes may require further investigation. |
| Description | Product description; may be absent or inconsistent. |
| Quantity | Units on the recorded line; negative values need interpretation. |
| InvoiceDate | Recorded date and time, parsed as supplied without a timezone claim. |
| UnitPrice | Price per unit in GBP. Zero/nonpositive prices require a stated policy. |
| CustomerID | Observed customer identifier; missing IDs must not be combined into one customer. |
| Country | Recorded customer country; not proof of nationality or preference. |

## Interpretation limits

- This is one historical UK retailer, including wholesale customers, not a sample of all commerce.
- Known customers and anonymous invoices have different selection mechanisms. Do not infer population missing-ID prevalence or revenue from the extract's ratios or totals.
- The source window ends on 9 December 2011. That month is incomplete; monthly totals are not automatically comparable.
- Repeated identical rows are not proven errors without an independent line identifier. Notebook deduplication is a policy with a sensitivity comparison.
- Positive recorded sales value is not profit, net revenue, or lifetime value. Returns and cancellations are excluded from that particular view rather than erased from the source.
- UCI's summary metadata and actual missing-value audit can disagree. Inspect the file rather than relying on a catalog flag.

## Alternatives for independent study

- [UCI Bank Marketing](https://archive.ics.uci.edu/dataset/222/bank+marketing): mixed categories, explicit `unknown` values, and questions about when a feature becomes available.
- [MovieLens Small](https://grouplens.org/datasets/movielens/): user–item or user–genre similarity. Follow provider terms and download from the source; it is not redistributed here.

These are optional candidates, not dependencies of Weeks 1–2.
