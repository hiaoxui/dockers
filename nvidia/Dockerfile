FROM pytorch/pytorch:2.5.1-cuda12.4-cudnn9-devel
LABEL maintainer="guanghuiqin@microsoft.com"

RUN curl https://sh.rustup.rs -sSf | sh -s -- -y
RUN pip install -U pip ninja packaging setuptools
RUN pip3 install torch torchvision triton -U --force-reinstall



RUN apt update && apt install -y git
RUN pip install flash-attn --no-build-isolation

COPY requirements.txt /tmp/requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt
# RUN pip install git+https://github.com/hiaoxui/transformers.git --no-build-isolation
