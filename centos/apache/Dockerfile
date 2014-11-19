############################################################
# Dockerfile to build Base container images
# Based on Centos
############################################################

# Set the base image
FROM            mostofreddy/centos:base

# File Author / Maintainer
MAINTAINER      Federico Lozada Mosto <mosto.federico@gmail.com>

################## BEGIN INSTALLATION ######################

# Add apps

RUN \
    yum install -y httpd httpd-devel

ADD supervisord.conf /etc/supervisord.conf

ADD httpd.conf /etc/httpd/conf/httpd.conf
ADD index.html /var/www/html/index.html

##################### INSTALLATION END #####################

EXPOSE 22 80
CMD ["/usr/bin/supervisord"]
