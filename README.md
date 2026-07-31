# Benchmarking Bowtie2, Minimap2, and GMAP

This project evaluates the performance of three sequence-alignment tools—Bowtie2, Minimap2, and GMAP—using synthetic paired-end DNA reads aligned to the human GRCh38.p13 reference genome.

The aligners were compared using 300 bp and 500 bp reads based on alignment accuracy, mapping performance, execution time, CPU usage, and memory consumption.

## Project files

- [Analysis notebook](alignment_benchmark.ipynb)
- [Full project report](alignment_benchmark_report.pdf)

## Workflow

The notebook:

1. Installs Bowtie2, Minimap2, GMAP, SAMtools, FastQC, and wgsim.
2. Downloads the GRCh38.p13 human reference genome.
3. Generates 10,000 synthetic paired-end read pairs for each read length.
4. Performs alignment with:
   - Bowtie2 in global and local modes
   - Minimap2 in sensitive and assembly modes
   - GMAP using paired-end SAM output
5. Processes the alignment files using SAMtools.
6. Extracts runtime, CPU, memory, mapping, mismatch, and error-rate statistics.
7. Produces tables and visualizations comparing the three aligners.

## Main findings

Minimap2 provided the strongest overall balance of alignment accuracy and computational efficiency. Bowtie2 showed competitive performance with comparatively moderate resource requirements, while GMAP required considerably more time and memory, particularly during indexing.

## Requirements

The complete workflow is intended for a Linux or Google Colab environment and requires substantial storage and memory because it downloads and indexes the GRCh38 reference genome.

Main tools and libraries:

- Bowtie2
- Minimap2
- GMAP
- SAMtools
- FastQC
- wgsim
- Python
- pandas
- matplotlib
- seaborn

## Reproducibility

The generated FASTQ, SAM, BAM, index, log, and reference-genome files are not included in this repository because of their size. They are generated or downloaded by the notebook.

The reported execution times and memory usage are dependent on the hardware and computational environment.

## Authors

- Asimenia Giagli
- Eva Mikraki-Petroula

National and Kapodistrian University of Athens
