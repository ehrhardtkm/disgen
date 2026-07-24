# disgen

A browser for a large sample dataset of **disordered atomic structures** spanning the
order→disorder spectrum (crystalline · nanocrystalline · LRO · MRO · SRO · amorphous),
generated with the disgen pipeline.

**Live:** https://ehrhardtkm.github.io/disgen/

> ⚠️ **Provisional / preview.** This dataset is still being finalized — the MRO regime has a
> known relative-density issue and will be regenerated. Structures downloaded through the
> browser are **display precision** (positions rounded to ~0.005 Å), not the exact simulation
> coordinates. For exact structures or the full dataset, contact **ehrdt@stanford.edu**.

## How it's put together

- **UI** (this repo, served via GitHub Pages): static HTML/JS/CSS + `data/dataset.parquet`
  (browsed client-side with DuckDB-Wasm) + `data/dataset.csv` (human-readable metadata).
- **Per-structure data** (3D `xyzq.gz`, g(r)/ADF `pdf.json`): hosted on the HuggingFace
  dataset **[ehrdt/disgen](https://huggingface.co/datasets/ehrdt/disgen)** and fetched at
  runtime. The base URL is set via `window.TRICOR_DATA_BASE` in each page's `<head>`.

Generated with the disgen pipeline (source: [ophusgroup/tricor](https://github.com/ophusgroup/tricor)).
