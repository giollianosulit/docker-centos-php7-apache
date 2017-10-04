FROM centos:latest

RUN rpm -Uvh https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
RUN rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm

RUN yum --enablerepo=remi-php70 install php php-devel php-gd php-xml php-mbstring php-opcache php-mcrypt php-mysqlnd -y

RUN yum clean all

# http port
# @TODO maybe 443 later on
EXPOSE 80

CMD /usr/sbin/httpd -DFOREGROUND