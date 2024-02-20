FROM continuumio/miniconda3:latest

RUN apt-get update && apt-get install -y --no-install-recommends vim git gcc build-essential gdb libnss-sss && rm -rf /var/lib/apt/lists* && apt-get clean \
    && conda install python=3.6 \
    && conda update -n base -c defaults conda \
    && conda install -c bioconda whatshap -y \
    && conda config --add channels defaults \
    && conda config --add channels bioconda \
    && conda config --add channels conda-forge \
    && conda install samtools=1.9

CMD ["/bin/bash"]
