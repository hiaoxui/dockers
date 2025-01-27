FROM nvcr.io/nvidia/pytorch:24.12-py3
LABEL maintainer="Guanghui Qin"

RUN pip install -U  pip ninja packaging setuptools setuptools-scm
RUN pip install     cmake wheel jinja2

RUN pip install vllm==0.6.6.post1
