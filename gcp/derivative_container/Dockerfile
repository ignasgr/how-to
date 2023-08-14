FROM gcr.io/deeplearning-platform-release/pytorch-gpu.2-0.py310:m109

# needed to avoid dependency error for NERDA 
ENV SKLEARN_ALLOW_DEPRECATED_SKLEARN_PACKAGE_INSTALL True
ENV TF_CPP_MIN_LOG_LEVEL 3

WORKDIR /root

RUN apt-get update && apt-get install -y \
    graphviz \
    python3-pydot \
    openssh-client

COPY requirements.txt .
RUN pip install -r requirements.txt --no-cache-dir
