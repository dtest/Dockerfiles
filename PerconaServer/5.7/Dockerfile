FROM percona:5.7
MAINTAINER dtestops@gmail.com

RUN deps=' \
    python-mysqldb \
  ' \
  && set -x \
  # Hack: to get around mysql-common package requiring a promt
  && mv /etc/mysql/my.cnf /tmp/my.cnf \
  && apt-get update \
  && apt-get install -y --no-install-recommends $deps \
  && rm -rf /var/lib/apt/lists/* \
  && mv /tmp/my.cnf /etc/mysql/my.cnf
