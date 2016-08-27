FROM dtestops/base
MAINTAINER downey@pythian.com

ENV PROXYSQL_VERSION=1.2.1

# TODO: be able to gpg verify download
RUN cd /tmp \
  && curl -SLO "https://github.com/sysown/proxysql/releases/download/v${PROXYSQL_VERSION}/proxysql_${PROXYSQL_VERSION}-ubuntu14_amd64.deb" \
  && dpkg -i "proxysql_$PROXYSQL_VERSION-ubuntu14_amd64.deb" \
  && apt-get install -f \
  && rm "proxysql_$PROXYSQL_VERSION-ubuntu14_amd64.deb"

ADD proxysql.cnf /etc/proxysql.cnf

RUN apt-get update && apt-get install -y \
  mysql-client-5.6 \
  && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/

EXPOSE 6032

CMD [ "proxysql", "--initial",  "-f", "-c /etc/proxysql.cnf" ]
