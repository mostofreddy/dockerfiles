############################################################
# Dockerfile to build Base container images
# Based on Ubuntu
############################################################

# Set the base image
FROM            freddy/centos:base

# File Author / Maintainer
MAINTAINER      Federico Lozada Mosto <mosto.federico@gmail.com>

################## BEGIN INSTALLATION ######################

# Add apps
RUN \
    curl -sL https://rpm.nodesource.com/setup | bash - && \
    yum -y update && \
    yum install -y nodejs && \
    npm install -g bower grunt-cli

##################### INSTALLATION END #####################
