FROM centos:6.7

MAINTAINER Taro <taross14.selkie@gmail.com>

RUN yum -y update
RUN yum -y groupinstall "base" "Development tools"
RUN yum clean all

RUN groupadd www-data
RUN useradd -d /home/www-data -g www-data -r -s /sbin/nologin www-data
