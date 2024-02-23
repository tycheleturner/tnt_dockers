FROM centos:7

COPY qmerRegionStats.cpp /qmerRegionStats.cpp
COPY filterVCFbySVsize.cpp /filterVCFbySVsize.cpp
COPY summarizeSVtype.cpp /summarizeSVtype.cpp
COPY filterVCFbySVsizeAndType.cpp /filterVCFbySVsizeAndType.cpp

# Download essentials for the following commands.
RUN yum update -y && \
	yum -y install wget tar vim git gcc build-essential gdb libnss-sss

# Download and install newer gcc compiler.
RUN yum -y groupinstall 'Development Tools'

# Download and install latest cmake.
RUN mkdir -p /tmp/cmake_download && \
	pushd /tmp/cmake_download && \
	wget -nv 'https://cmake.org/files/v3.13/cmake-3.13.2-Linux-x86_64.sh' && \
	bash cmake-3.13.2-Linux-x86_64.sh --prefix=/usr/local --exclude-subdir && \
	popd && \
	rm -rf /tmp/cmake_download

# Download and install openssl
RUN yum -y install openssl-devel

# Download and install libcurl
RUN yum -y install libcurl-devel

# Download and install libxml2
RUN yum -y install libxml2-devel

# clean up
RUN yum clean all

# install qmerRegions
RUN g++ -std=c++11 /qmerRegionStats.cpp -o /qmerRegionStats -lz 
RUN g++ -std=c++11 /filterVCFbySVsize.cpp -o /filterVCFbySVsize -lz
RUN g++ -std=c++11 /summarizeSVtype.cpp -o /summarizeSVtype -lz
RUN g++ -std=c++11 /filterVCFbySVsizeAndType.cpp -o /filterVCFbySVsizeAndType -lz

RUN rm /qmerRegionStats.cpp
RUN rm /filterVCFbySVsize.cpp
RUN rm /summarizeSVtype.cpp
RUN rm /filterVCFbySVsizeAndType.cpp

