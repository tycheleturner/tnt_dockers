FROM continuumio/miniconda3:latest

RUN apt-get update && apt-get install -y --no-install-recommends git gcc build-essential gdb libnss-sss && rm -rf /var/lib/apt/lists* \
    && conda install python=3.9 \
    && conda install -c bioconda numpy matplotlib\
    && conda install -c conda-forge -c bioconda snakemake \
    && conda install -c biocore memsat-svm disopred psipred \
    && conda config --add channels defaults \
    && conda config --add channels bioconda \
    && conda config --add channels conda-forge

CMD ["/bin/bash"]
