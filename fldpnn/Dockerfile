FROM ubuntu:20.04
ENV PATH="/root/miniconda3/bin:${PATH}"
ARG PATH="/root/miniconda3/bin:${PATH}"
RUN apt-get update -y
RUN DEBIAN_FRONTEND=noninteractive apt-get -yq install git openjdk-8-jre libidn11 tcsh wget
WORKDIR /home
RUN git clone https://gitlab.com/sina.ghadermarzi/fldpnn.git
RUN wget \
    https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh \
    && mkdir /root/.conda \
    && bash Miniconda3-latest-Linux-x86_64.sh -b \
    && rm -f Miniconda3-latest-Linux-x86_64.sh

RUN /root/miniconda3/bin/conda env create -p cenv/ -f fldpnn/enviornment.yml
# SHELL ["/bin/bash", "-c", "source /home/biomine/anaconda3/bin/activate /home/cenv/"]

ENTRYPOINT  ["/bin/bash"]


