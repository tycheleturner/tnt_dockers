FROM continuumio/miniconda3:latest

COPY script.py /script.py

RUN apt-get update && apt-get install -y --no-install-recommends libcurl4-openssl-dev libssl-dev vim git gcc build-essential gdb libnss-sss wget && rm -rf /var/lib/apt/lists* \
    && conda install python=3.8 \
    && pip3 install fastrand \
    && pip3 install wget \
    && pip3 install SigProfilerSimulator \
    && pip3 install SigProfilerMatrixGenerator \
    && python /script.py

CMD ["/bin/bash"]
