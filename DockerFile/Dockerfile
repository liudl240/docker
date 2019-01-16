FROM centos:7.5.1804

ADD usr/local/src/jdk1.8.0_131 /usr/local/src/jdk1.8.0_131
ADD kafka_2.11-2.1.0 kafka
ADD etc/profile /etc/profile
ADD /usr/local/lib/libsasl2.so.2.0.25 /usr/local/lib/libsasl2.so.2.0.25
ADD etc/ld.so.conf.d/sasl2.conf /etc/ld.so.conf.d/sasl2.conf
ADD /etc/yum.repos.d /etc/yum.repos.d

RUN mkdir -pv /usr/lib/x86_64-linux-gnu/sasl2 /usr/lib/sasl2
RUN ln -s  /usr/local/lib/libsasl2.so.2.0.25  /usr/local/lib/libsasl2.so.2
RUN yum -y install net-tools 
RUN yum -y install mysql-community-libs
RUN source /etc/profile
RUN ldconfig -v 
entrypoint /bin/bash
