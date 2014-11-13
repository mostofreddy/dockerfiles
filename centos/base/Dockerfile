############################################################
# Dockerfile to build Base container images
# Based on Centos
############################################################

# Set the base image to CentOS
FROM            centos:centos6

# File Author / Maintainer
MAINTAINER      Federico Lozada Mosto <mosto.federico@gmail.com>

# Update the repository sources list
RUN \
    yum -y update && \
    yum -y upgrade

################## BEGIN INSTALLATION ######################

# Add apps
RUN \
    yum groupinstall -y 'Development Tools' && \
    yum install -y vim wget unzip man htop ssh

##################### INSTALLATION END #####################
