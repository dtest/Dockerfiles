FROM dtestops/base
MAINTAINER downey@pythian.com

# TODO: be able to gpg verify download
RUN cd /tmp \
  && curl -SLO "http://downloads.mysql.com/snapshots/pb/mysql-innodb-cluster-5.7.15-preview/mysql-innodb-cluster-labs201609-el7-x86_64.rpm.tar.gz" \
  # && dpkg -i "proxysql_$PROXYSQL_VERSION-ubuntu14_amd64.deb" \
  # && apt-get install -f \
  # && rm "proxysql_$PROXYSQL_VERSION-ubuntu14_amd64.deb"

# ADD proxysql.cnf /etc/proxysql.cnf

# RUN deps=' \
#     mysql-client-5.6 \
#     libmysqlclient-dev \
#     zlib1g-dev \
#   ' \
#   && set -x \
#   && apt-get update \
#   && apt-get install -y --no-install-recommends $deps \
#   && rm -rf /var/lib/apt/lists/*

# RUN pip install MySQL-python

# EXPOSE 6032

# CMD [ "proxysql", "--initial",  "-f", "-c /etc/proxysql.cnf" ]

CMD [ "bash" ]