FROM continuumio/miniconda3:latest

RUN apt-get update && apt-get install -y --no-install-recommends vim git gcc build-essential gdb libnss-sss && rm -rf /var/lib/apt/lists* \
    && conda install python=3.6 \
    && conda update -n base -c defaults conda \
    && conda install -c bioconda bwa R bedtools bcftools picard samtools=1.9 hifiasm -y

CMD ["/bin/bash"]
