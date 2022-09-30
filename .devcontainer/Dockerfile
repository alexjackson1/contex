FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu

RUN apt-get update && apt-get install -y \
  chktex \
  latexmk \
  texlive-full \
  unzip \
  wget \
  && rm -rf /var/lib/apt/lists/*

ARG TEXCOUNT_VERSION="3_2_0_41"
WORKDIR /usr/src/texcount

RUN wget -O texcount.zip https://app.uio.no/ifi/texcount/download.php?file=texcount_${TEXCOUNT_VERSION}.zip && \
  unzip texcount.zip texcount.pl && \
  rm texcount.zip && \
  mv texcount.pl /usr/bin/texcount && \
  chmod +x /usr/bin/texcount && \
  apt-get remove -y wget unzip && \
  rm -rf /usr/src/texcount