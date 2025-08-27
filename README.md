
# Single-Cell RNA-Seq Pipeline Evaluation — Sample SRR12727766

This repository evaluates the **nf-core/scnanoseq** pipeline for processing Oxford Nanopore single-cell RNA-seq data. The dataset used corresponds to a sample under accession **SRR12727766** from the SRA archive.

## 🔗 Data Source

- **Accession**: [SRR12727766](https://www.ebi.ac.uk/ena/browser/view/SRR12727766)
- **Size**: ~500MB (subsampled as needed)

## 🧪 Pipeline Overview (nf-core/scnanoseq)

This Nextflow-based pipeline performs the following steps:

1. **Quality Control**:
   - Tool: `FastQC`
   - Filters low-quality reads before processing

2. **Basecalling**:
   - Tool: `Guppy` or similar
   - Converts raw nanopore signals into FASTQ

3. **Barcode Extraction and Correction**:
   - Handles demultiplexing of single-cell barcodes
   - Filters barcodes based on abundance

4. **Alignment**:
   - Tool: `minimap2`
   - Maps reads to the human reference genome (GRCh38)

5. **Gene Quantification**:
   - Counts gene-level expression using long-read quantifiers

## 📂 Folder Structure

```
project/
├── data/
│   └── SRR12727766.fastq
├── workflow/
│   └── run_pipeline.sh (or nf-core/scnanoseq command)
├── questions.yaml
├── answers.yaml
├── metadata.yaml
└── README.md
```

## ⚠️ Note

- This workflow expects subsampled FASTQ input (<100MB) to comply with Taiga platform limits.
- All components (data and code) are packaged accordingly.
