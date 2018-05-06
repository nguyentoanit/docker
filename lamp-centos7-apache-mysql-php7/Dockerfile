FROM nguyentoanit/centos7-systemd:latest
MAINTAINER nguyentoanit

RUN yum update -y && yum install -y httpd mariadb-server mariadb epel-release http://rpms.remirepo.net/enterprise/remi-release-7.rpm && yum-config-manager --enable remi-php72 && yum install -y php php-mysqlnd php-pdo

# start on boot
RUN systemctl enable httpd.service mariadb.service

CMD ["/usr/sbin/init"]
