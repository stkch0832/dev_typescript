# ベースイメージ: Ubuntu
FROM ubuntu:22.04

# 非対話モード設定 & 基本ツールのインストール
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    curl \
    git \
    gnupg \
    ca-certificates \
    build-essential \
    vim \
    sudo

# Node.js のインストール（LTS）
RUN curl -fsSL https://deb.nodesource.com/setup_18.x | bash - && \
    apt-get install -y nodejs

# TypeScript グローバルインストール
RUN npm install -g typescript eslint

# デフォルトの作業ディレクトリ
WORKDIR /workspace

# VSCodeの設定（拡張機能の競合回避）
COPY ../.vscode /workspace/.vscode
