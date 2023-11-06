# 丹生さんのCWL for remote container(https://github.com/tom-tan/cwl-for-remote-container-template/tree/master)を参考にしました

# Get arguments for python version (in this case, python 3.9 image is used)

ARG VARIANT="3.9-bullseye"
FROM mcr.microsoft.com/vscode/devcontainers/python:0-${VARIANT}

# Install additional packages
# Install R and rpy2 dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    r-base \
    r-base-dev \
    libcurl4-gnutls-dev \
    libssl-dev \
    libxml2-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Install rpy2
RUN pip install --upgrade pip
RUN pip install rpy2

# Install R packages
RUN R -e "install.packages('BiocManager', repos = 'http://cran.us.r-project.org')"
RUN R -e "BiocManager::install('enrichplot')"

# 1. 必要なパッケージのインストール
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
    python-circos

# Jupyter Notebookの設定
RUN python3 -m ipykernel install --user