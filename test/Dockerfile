FROM centos:latest

RUN yum install epel-release -y

RUN yum install wget -y

RUN yum install httpd -y

EXPOSE 80

ENTRYPOINT ["/usr/sbin/httpd", "-D", "FOREGROUND"]
