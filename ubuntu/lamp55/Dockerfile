############################################################
# Dockerfile to build Base container images
# Based on Ubuntu
############################################################

# Set the base image
FROM            freddy/ubuntu:base

# File Author / Maintainer
MAINTAINER      Federico Lozada Mosto <mosto.federico@gmail.com>

################## BEGIN INSTALLATION ######################

# Add apps
RUN \
    apt-get install -y apache2 && \
    apt-get -y clean

##################### INSTALLATION END #####################

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2

EXPOSE 80

CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]