FROM gcramdcr.azurecr.io/gcr-rocm6.3-ubuntu2204-dev:v1

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install software-properties-common -y && \
    add-apt-repository -y ppa:deadsnakes/ppa && \
    DEBIAN_FRONTEND=noninteractive apt-get install --no-install-recommends -y \
        ca-certificates \
        g++ \
        python3-distutils \
        python3 \
        python3-dev \
        python3-venv \
        openjdk-17-jdk \
        curl \
        git \
        cmake \
    && rm -rf /var/lib/apt/lists/*

RUN pip install ninja


RUN git clone --recursive https://github.com/pytorch/pytorch && \
    cd pytorch && \
    git submodule sync && \
    git submodule update --init --recursive && \
    pip3 install --no-cache-dir -r requirements.txt && \
    pip install mkl-static mkl-include && \
    cd ..

RUN cd pytorch && \
    python tools/amd_build/build_amd.py && \
    python3 setup.py develop

