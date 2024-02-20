FROM continuumio/miniconda3:latest

RUN apt-get update && apt-get install -y --no-install-recommends vim git gcc build-essential gdb libnss-sss && rm -rf /var/lib/apt/lists* && apt-get clean \
    && conda install python=3.8 \
    && conda update -n base -c defaults conda \
    && conda install -c bioconda lima isoseq3 pbmm2 pbpigeon -y \
    && conda config --add channels defaults \
    && conda config --add channels bioconda \
    && conda config --add channels conda-forge

CMD ["/bin/bash"]
