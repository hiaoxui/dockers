FROM gcramdcr.azurecr.io/rocm/vllm0.6.3-rocm6.2-pytorch2.6-singularity:0.1
LABEL maintainer="guanghuiqin@microsoft.com"

RUN curl https://sh.rustup.rs -sSf | sh -s -- -y
RUN pip install -U pip

COPY requirements.txt /tmp/requirements.txt 
RUN pip install --no-cache-dir -r /tmp/requirements.txt && rm /tmp/requirements.txt
RUN pip install git+https://github.com/hiaoxui/transformers.git

# triton
# RUN pip uninstall pytorch-triton-rocm triton -y
# RUN git clone https://github.com/ROCm/triton.git && \
#       cd triton/python && \
#       GPU_ARCHS=gfx942 python setup.py install 
    
RUN git clone https://github.com/ROCm/xformers.git && \
    cd xformers/ && \
    git submodule update --init --recursive && \
    PYTORCH_ROCM_ARCH=gfx942 python setup.py install #Instinct MI300-series

RUN pip install --no-cache-dir mistral_common==1.5.1 mistral_inference==1.5.0
