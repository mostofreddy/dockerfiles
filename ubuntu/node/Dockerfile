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
    curl -sL https://deb.nodesource.com/setup | sudo bash - && \
    apt-get -y update && \
    apt-get install -y nodejs && \
    npm install -g bower grunt-cli


##################### INSTALLATION END #####################
