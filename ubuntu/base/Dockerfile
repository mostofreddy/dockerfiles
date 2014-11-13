############################################################
# Dockerfile to build Base container images
# Based on Ubuntu
############################################################

# Set the base image to Ubuntu
FROM            ubuntu:14.04

# File Author / Maintainer
MAINTAINER      Federico Lozada Mosto <mosto.federico@gmail.com>

# Update the repository sources list
RUN \
    apt-get -y update && \
    apt-get -y upgrade

################## BEGIN INSTALLATION ######################

# Languaje
RUN locale-gen en_US.UTF-8
RUN update-locale LANG=en_US.UTF-8
ENV LANG       en_US.UTF-8
ENV LC_ALL     en_US.UTF-8

# Add apps
RUN \
    apt-get -y --no-install-recommends install build-essential automake make cmake libtool autoconf && \
    apt-get -y --no-install-recommends install p7zip-full arj unzip && \
    apt-get -y --no-install-recommends install vim curl ssh wget htop man bash-completion && \
    apt-get -y --no-install-recommends install subversion colordiff git git-core && \
    apt-get clean autoremove

##################### INSTALLATION END #####################

CMD ["bash"]
