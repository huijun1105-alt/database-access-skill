---
name: database-access
description: Access NCBI and UniProt databases, download sequences, query SRA/GEO, and run BLAST-style searches for bioinformatics data acquisition workflows.
metadata:
  source-repo: https://github.com/GPTomics/bioSkills/tree/ebe4f4003ebeef4beda84ae1fb4f52295848c4e1/database-access
  install-note: Wrapped from upstream README because the referenced directory does not contain a native Codex SKILL.md.
---

# database-access

## Overview

Access NCBI and UniProt databases, download sequences, query SRA/GEO, and run BLAST searches. Often the starting point of bioinformatics workflows for fetching data before local processing.

Tool type: mixed
Primary tools: `Bio.Entrez`, `Bio.Blast`, SRA Toolkit, BLAST+, UniProt REST API

## Skills Covered

- `entrez-search`: Search NCBI databases with ESearch, EInfo, EGQuery
- `entrez-fetch`: Retrieve records by ID with EFetch, ESummary
- `entrez-link`: Cross-database references with ELink
- `batch-downloads`: Large-scale downloads using history server and batching
- `sra-data`: Download SRA sequencing reads with `fasterq-dump`, `prefetch`
- `geo-data`: Query GEO expression datasets and link GEO to SRA
- `blast-searches`: Remote BLAST searches via NCBI
- `local-blast`: Local BLAST databases and searches with BLAST+
- `sequence-similarity`: PSI-BLAST, HMMER, reciprocal best hits for remote homologs
- `uniprot-access`: Query UniProt, perform ID mapping, and batch retrieval
- `interaction-databases`: Query STRING, BioGRID, and IntAct interaction databases

## Example Prompts

- Find PubMed articles about CRISPR published in 2024.
- Download the GenBank record for `NM_001234`.
- Download all RefSeq mRNA sequences for human `TP53`.
- Find all proteins linked to this gene ID.
- Download the FASTQ files for SRA accession `SRR12345678`.
- Find GEO datasets for breast cancer RNA-seq.
- BLAST this sequence against the `nr` database.
- Set up a local BLAST database from my sequences.
- Run `blastp` on my protein against the Swiss-Prot database.
- Find remote homologs with PSI-BLAST.
- Search Pfam with my protein sequence.
- Find orthologs between two species.
- Get the taxonomy ID for `Escherichia coli K-12`.
- Fetch gene information for human `BRCA1`.
- Find all human kinases in UniProt.
- Download the UniProt entry for `P53_HUMAN`.
- Map these gene symbols to UniProt IDs.
- Get protein-protein interactions for my gene list from STRING.
- Build an interaction network from BioGRID and IntAct.

## Requirements

```bash
pip install biopython
conda install -c bioconda sra-tools
conda install -c bioconda blast
conda install -c bioconda hmmer
```

## Local Environment Notes

- `biopython` is already available in this environment.
- `prefetch`, `fasterq-dump`, `blastn`, `blastp`, and `hmmscan` were not present at install time.
- If you want the full workflow support from this skill, install the missing command-line tools into the environment Codex uses.

## Related Skills

- `sequence-io`
- `sequence-manipulation`
- `alignment-files`
- `variant-calling`
- `gene-regulatory-networks`
- `data-visualization`
