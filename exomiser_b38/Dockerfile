FROM continuumio/miniconda3:latest

COPY ReMM.v0.3.1.hg38.sort.final.tsv.gz /ReMM.v0.3.1.hg38.sort.final.tsv.gz
COPY ReMM.v0.3.1.hg38.sort.final.tsv.gz.tbi /ReMM.v0.3.1.hg38.sort.final.tsv.gz.tbi

RUN apt-get update && apt-get install -y --no-install-recommends vim git gcc build-essential gdb libnss-sss wget unzip zip && rm -rf /var/lib/apt/lists* && apt-get clean \
    && conda install python=3.6 \
    && conda update -n base -c defaults conda \
    && conda install -c bioconda R pysam pysamstats hdf5 bedtools bcftools picard biopython -y \
    && conda install -c conda-forge -c bioconda snakemake \
    && conda config --add channels defaults \
    && conda config --add channels bioconda \
    && conda config --add channels conda-forge \
    && wget https://data.monarchinitiative.org/exomiser/latest/exomiser-cli-12.1.0-distribution.zip && unzip exomiser-cli-12.1.0-distribution.zip

CMD ["/bin/bash"]
