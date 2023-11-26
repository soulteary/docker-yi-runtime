FROM nvcr.io/nvidia/pytorch:23.10-py3
RUN pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple && \
    pip3 install --upgrade pip  # enable PEP 660 support
RUN sed -i 's/archive.ubuntu.com/mirrors.tuna.tsinghua.edu.cn/g' /etc/apt/sources.list && \
	sed -i 's/security.ubuntu.com/mirrors.tuna.tsinghua.edu.cn/g' /etc/apt/sources.list
WORKDIR /app
RUN pip3 install transformers==4.35.0 huggingface-hub==0.17.3 hf_transfer==0.1.4
RUN apt-get update && apt-get install cmake -y && apt-get autoremove -y