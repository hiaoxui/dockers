FROM rocm/pytorch:rocm6.3_ubuntu22.04_py3.10_pytorch_release_2.5.1_preview
LABEL maintainer="guanghuiqin@microsoft.com"

RUN curl https://sh.rustup.rs -sSf | sh -s -- -y
RUN pip install -U pip ninja packaging setuptools

RUN git clone https://github.com/ROCm/flash-attention.git && \
    cd flash-attention/ && \
    GPU_ARCHS=gfx942 python setup.py install
