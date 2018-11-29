FROM centos:7
MAINTAINER your name <your@email.com>
ENV http_proxy http://70.10.15.10:8080
ENV https_proxy http://70.10.15.10:8080
RUN export http_proxy=http://70.10.15.10:8080
RUN yum makecache
RUN yum -y install epel-release
RUN yum -y install httpd
EXPOSE 80 443
CMD ["/usr/sbin/httpd", "-DFOREGROUND"]

# docker build --build-arg http_proxy=http://70.10.15.10:8080 --build-arg https_proxy=http://70.10.15.10:8080 -t example1 .
# docker build -t example1 .