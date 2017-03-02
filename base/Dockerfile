FROM ubuntu:14.04
MAINTAINER dtestops@gmail.com

RUN deps=' \
    curl \
    ca-certificates \
    unzip \
  ' \
  && set -x \
  && apt-get update \
  && apt-get install -y --no-install-recommends $deps \
  && rm -rf /var/lib/apt/lists/*

RUN deps=' \
    gcc \
    python \
    python-dev \
    python-pip \
  ' \
  && set -x \
  && apt-get update \
  && apt-get install -y --no-install-recommends $deps \
  && rm -rf /var/lib/apt/lists/*
