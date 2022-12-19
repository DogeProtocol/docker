FROM ubuntu:22.04
RUN apt update && apt install -y astyle cmake gcc ninja-build libssl-dev python3-pytest python3-pytest-xdist unzip xsltproc doxygen graphviz python3-yaml valgrind git && rm -rf /var/lib/apt/lists/* && apt clean
RUN git clone -b main https://github.com/open-quantum-safe/liboqs.git
WORKDIR liboqs
RUN mkdir build
WORKDIR build
RUN pwd
RUN cmake -G Ninja -DBUILD_SHARED_LIBS=ON ..
RUN ninja
RUN ninja run_tests

