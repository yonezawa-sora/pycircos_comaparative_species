# 丹生さんのCWL for remote container(https://github.com/tom-tan/cwl-for-remote-container-template/tree/master)を参考にしました

# Get arguments for python version (in this case, python 3.9 image is used)

ARG VARIANT="3.9-bullseye"
FROM mcr.microsoft.com/vscode/devcontainers/python:0-${VARIANT}

# Install additional packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    r-base \
    r-base-dev 

# update pip
RUN pip install --upgrade pip

# Install python packages
RUN pip install \
    openai \ 
    biopython \ 
    google \
    gspread \ 
    pandas \ 
    numpy \
    matplotlib \ 
    scipy \
    statsmodels \
    seaborn \ 
    jupyter \ 
    ipykernel \ 
    urllib3 \ 
    retry \ 
    PyYAML \ 
    requests \ 
    python-dotenv \
    python-circos \
    gprofiler-official \
    polars

# Jupyter Notebookの設定
RUN python3 -m ipykernel install --user