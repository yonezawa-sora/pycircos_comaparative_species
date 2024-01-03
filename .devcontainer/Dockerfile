# Reference: https://github.com/tom-tan/cwl-for-remote-container-template/tree/master

# Get arguments for python version (in this case, python 3.9 image is used)
ARG VARIANT="3.9-bullseye"
FROM mcr.microsoft.com/vscode/devcontainers/python:0-${VARIANT}

# Install additional packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    r-base \
    r-base-dev 

# upgrade pip & install python packages
RUN pip install \ 
    --upgrade pip \
    numpy==1.26.2 \ 
    pandas==2.1.4 \ 
    matplotlib==3.8.2 \ 
    seaborn==0.13.1 \ 
    SciPy==1.11.4 \
    statsmodels==0.14.1 \
    jupyter==1.0.0 \ 
    ipykernel==6.28.0 \ 
    urllib3==2.1.0 \
    retry==0.9.2 \
    PyYAML==6.0.1 \ 
    requests==2.31.0 \ 
    python-circos==0.3.0 \
    polars==0.20.3

# Jupyter Notebook Setting
RUN python3 -m ipykernel install --user