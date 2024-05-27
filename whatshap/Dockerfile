FROM continuumio/miniconda3:latest

RUN apt-get update && apt-get install -y --no-install-recommends vim git gcc build-essential gdb libnss-sss && rm -rf /var/lib/apt/lists* && apt-get clean \
    && conda install python=3.9 pip \
    && pip install --user whatshap

CMD ["/bin/bash"]
