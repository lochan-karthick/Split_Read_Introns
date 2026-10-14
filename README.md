
# Split-Read Intron Detection from SAM Alignments

This repository contains a Python script for identifying introns from split-read alignments in SAM files and mapping the detected intron junctions to annotated genes.

## Overview

In RNA sequencing data, reads spanning exon-exon junctions provide evidence of introns. These split reads can be identified using the CIGAR strings in SAM alignment files.

The script processes uniquely mapped reads, identifies skipped genomic regions (`N` in CIGAR strings), calculates intron coordinates, and maps the detected junctions to genes based on their genomic locations. It also counts the number of reads supporting each junction.

## Files

| File | Description |
|---|---|
| `split_read_introns.py` | Main Python script for detecting intron junctions and counting supporting reads. |
| `GenesByLocation_Summary.txt` | Gene annotation file containing gene IDs and genomic coordinates. |
| `Split_read_introns.txt` | Previously generated intron detection results. |
| `example_output.txt` | Example of the expected output format. |

## Requirements

- Python 3
- A SAM alignment file
- A tab-delimited gene annotation file containing gene IDs and genomic locations

The script uses Python's standard library and requires no additional Python packages.

## Usage

Run the script from the command line:

    python3 split_read_introns.py reads.sam GenesByLocation_Summary.txt

Replace `reads.sam` with the path to your SAM alignment file.

The script generates `generated_introns.txt`, containing the detected junctions and their supporting read counts.

## Output

| Column | Description |
|---|---|
| Gene ID | Gene associated with the detected junction. |
| Junction Start | Genomic start coordinate of the intron. |
| Junction End | Genomic end coordinate of the intron. |
| Read Count | Number of uniquely mapped reads supporting the junction. |

An example output is provided in `example_output.txt`.

The original SAM alignment file is not included in this repository.
