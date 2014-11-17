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
    apt-get -y install apache2 && \
    apt-get clean

##################### INSTALLATION END #####################

EXPOSE 80
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
