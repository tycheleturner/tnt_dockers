FROM tychelewustl/julia:dfvcfap3

# Install system packages required for Miniconda
RUN apt-get update && apt-get install -y wget bzip2 ca-certificates \
    libglib2.0-0 libxext6 libsm6 libxrender1 \
    git mercurial subversion

# Download and install Miniconda
RUN wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O /miniconda.sh && \
    bash /miniconda.sh -b -p /miniconda && \
    rm /miniconda.sh

# Put conda in path so we can use conda activate
ENV PATH=/miniconda/bin:$PATH

# Create a conda environment and install snakemake
RUN conda create -n env python=3.9 -y && \
    echo "source activate env" > ~/.bashrc && \
    . /miniconda/bin/activate env && \
    conda install -c bioconda -c conda-forge snakemake -y

# Set the working directory in the container
WORKDIR /usr/src/app

CMD ["/bin/bash"]
