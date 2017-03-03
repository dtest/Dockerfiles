FROM percona:5.6
MAINTAINER dtestops@gmail.com

RUN deps=' \
    python-mysqldb \
  ' \
  && set -x \
  && apt-get update \
  && apt-get install -y --no-install-recommends $deps \
  && rm -rf /var/lib/apt/lists/*
