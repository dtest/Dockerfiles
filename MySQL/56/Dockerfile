FROM mysql/mysql-server:5.6
MAINTAINER dtestops@gmail.com

RUN set -x \
  && yum --enablerepo='ol7_MySQL56*' install -y MySQL-python \
  && yum clean all
