FROM mysql/mysql-server:5.7
MAINTAINER dtestops@gmail.com

RUN set -x \
  && yum --enablerepo='ol7_MySQL57*' install -y MySQL-python \
  && yum clean all
