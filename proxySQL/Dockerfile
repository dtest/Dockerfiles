FROM dtestops/base
MAINTAINER downey@pythian.com

ENV PROXYSQL_VERSION=1.3.4

# TODO: be able to gpg verify download
RUN cd /tmp \
  && curl -SLO "https://github.com/sysown/proxysql/releases/download/v${PROXYSQL_VERSION}/proxysql_${PROXYSQL_VERSION}-ubuntu14_amd64.deb" \
  && dpkg -i "proxysql_$PROXYSQL_VERSION-ubuntu14_amd64.deb" \
  && apt-get install -f \
  && rm "proxysql_$PROXYSQL_VERSION-ubuntu14_amd64.deb"

ADD proxysql.cnf /etc/proxysql.cnf

RUN deps=' \
    mysql-client-5.6 \
    libmysqlclient-dev \
    zlib1g-dev \
    git \
  ' \
  && set -x \
  && apt-get update \
  && apt-get install -y --no-install-recommends $deps \
  && rm -rf /var/lib/apt/lists/*

RUN pip install MySQL-python

EXPOSE 6032

CMD [ "proxysql", "--initial",  "-f", "-c /etc/proxysql.cnf" ]
