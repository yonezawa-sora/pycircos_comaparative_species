# 丹生さんのCWL for remote container(https://github.com/tom-tan/cwl-for-remote-container-template/tree/master)を参考にしました

# Get arguments for python version (in this case, python 3.9 image is used)

ARG VARIANT="3.9-bullseye"
FROM mcr.microsoft.com/vscode/devcontainers/python:0-${VARIANT}

# Install additional packages
# ここは必要に応じて変更する予定です

# 0. pipのアップデート(念のため)
RUN pip install --upgrade pip

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