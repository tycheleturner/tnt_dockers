FROM continuumio/miniconda3:latest

RUN apt-get update && apt-get install -y --no-install-recommends vim git gcc build-essential gdb libnss-sss libz-dev && rm -rf /var/lib/apt/lists* \
    && conda install python=3.7 pip \
    && conda update -n base -c defaults conda \
    && conda install -c bioconda minimap2 -y \
    && conda config --add channels defaults \
    && conda config --add channels bioconda \
    && conda install samtools=1.9 \
    && git clone https://github.com/lh3/gfatools \
    && cd gfatools && make

CMD ["/bin/bash"]
