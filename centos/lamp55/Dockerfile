############################################################
# Dockerfile to build Base container images
# Based on Centos
############################################################

# Set the base image
FROM            freddy/centos:base

# File Author / Maintainer
MAINTAINER      Federico Lozada Mosto <mosto.federico@gmail.com>

################## BEGIN INSTALLATION ######################

# Add apps

RUN \
    yum install -y httpd httpd-devel

RUN cd /root
RUN yum install -y libxml2-devel openssl-devel libcurl-devel libjpeg-devel libpng-devel freetype-devel readline-devel net-snmp net-snmp-devel libxslt-devel
RUN wget http://pkgs.repoforge.org/rpmforge-release/rpmforge-release-0.5.3-1.el6.rf.x86_64.rpm
RUN rpm -i rpmforge-release-0.5.3-1.el6.rf.*.rpm
RUN yum install -y libmcrypt-devel
RUN rm rpmforge-release-0.5.3-1.el6.rf.*.rpm

RUN \
    cd /root && \
    wget http://ar2.php.net/get/php-5.5.18.tar.gz/from/this/mirror && \
    mv mirror php-5.5.18.tar.gz && \
    tar xvzf php-5.5.18.tar.gz

RUN \
    cd /root && \
    cd php-5.5.18 && \
    ./configure \
        --prefix=/usr/local/php/php_5.5.18 \
        --with-apxs2 \
        --disable-all \
        --enable-session \
        --enable-libxml \
        --enable-dom \
        --enable-filter \
        --enable-pdo \
        --enable-phar \
        --enable-simplexml \
        --enable-soap \
        --enable-sockets \
        --enable-bcmath \
        --enable-ftp \
        --enable-mbstring \
        --enable-tokenizer \
        --enable-xml \
        --enable-mysqlnd \
        --with-sqlite3 \
        --with-libxml-dir=/usr/bin \
        --with-openssl \
        --with-openssl-dir=/usr/bin \
        --with-zlib \
        --with-curl \
        --with-gettext \
        --with-mysql=mysqlnd \
        --with-mysqli=mysqlnd \
        --with-readline \
        --with-pdo-mysql=mysqlnd \
        --with-pdo-sqlite \
        --with-snmp \
        --with-openssl-dir \
        --with-pear \
        --enable-mysqlnd-compression-support \
        --enable-inline-optimization \
        --with-zend-vm=GOTO \
        --enable-static \
        --enable-re2c-cgoto \
        --enable-cli \
        --enable-json \
        --with-iconv \
        --with-mcrypt \
        --with-mhash \
        --enable-ctype \
        --enable-xmlwriter \
        --enable-xmlreader \
        --enable-posix \
        --enable-ipv6 \
        --enable-calendar \
        --with-xsl \
        --with-gd \
        --with-freetype-dir \
        --with-jpeg-dir \
        --with-png-dir

RUN \
    cd /root && \
    cd php-5.5.18 && \
    make clean && \
    make && \
    make install && \
    cp php.ini-development /usr/local/php/php_5.5.18/lib/php.ini && \
    cd .. && \
    rm php-5.5.18 -Rf && \
    rm php-5.5.18.tar.gz

ADD supervisord.conf /etc/supervisord.conf

##################### INSTALLATION END #####################

EXPOSE 22 80
CMD ["/usr/bin/supervisord"]
