FROM continuumio/miniconda3:latest

RUN apt-get update && apt-get install -y --no-install-recommends git gcc build-essential gdb libnss-sss && rm -rf /var/lib/apt/lists* \
    && conda install python=3.6 \
    && conda install -c bioconda mrsfast picard bwa=0.7.15 samtools=1.9 numpy=1.16.2 matplotlib\
    && conda install -c conda-forge -c bioconda snakemake \
    && conda config --add channels defaults \
    && conda config --add channels bioconda \
    && conda config --add channels conda-forge

CMD ["/bin/bash"]
