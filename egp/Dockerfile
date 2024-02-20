FROM continuumio/miniconda3:latest

COPY script.R /script.R

RUN apt-get update && apt-get install -y --no-install-recommends vim git gcc build-essential gdb libnss-sss && rm -rf /var/lib/apt/lists* \
    && conda install python=3.6 \
    && conda update -n base -c defaults conda \
    && conda install -c bioconda R pysam pysamstats hdf5 bcftools picard biopython -y \
    && conda install -c conda-forge -c bioconda snakemake \
    && conda config --add channels defaults \
    && conda config --add channels bioconda \
    && conda config --add channels conda-forge \
    && conda install samtools=1.9 \
    && Rscript /script.R \

CMD ["/bin/bash"]
