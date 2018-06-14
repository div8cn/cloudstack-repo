FROM centos:7.5.1804

ENV CLOUDSTACK_VERSION 4.11rc2
ENV OS_VERSION centos7.5.1804

RUN curl -o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo \
  &&curl -o /etc/yum.repos.d/epel.repo http://mirrors.aliyun.com/repo/epel-7.repo \
  && curl -o /etc/yum.repos.d/cloudstac.repo https://raw.githubusercontent.com/div8cn/cloudstack-repo/master/centos/4111rc2 \
  && rpm -Uvh http://dev.mysql.com/get/mysql-community-release-el7-5.noarch.rpm \
  && rpm -import /etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7 \
  && rpm -import /etc/pki/rpm-gpg/RPM-GPG-KEY-mysql \
  && rpm -import http://packages.shapeblue.com/release.asc \
  && yum repolist enabled | grep "mysql.*-community.*" \
  && yum install -y cloudstack-management \
  && yum clean all \
  && rm -rf /var/cache/yum

