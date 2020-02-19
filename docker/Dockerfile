FROM opensuse/leap

ENV LANG=en_GB.UTF-8

RUN zypper -n update

RUN zypper -n install \
        apache2 \
        apache2-devel \
        apache2-mod_wsgi \
        bind-utils \
        command-not-found \
        coreutils \
        findutils \
        gcc \
        gcc-c++ \
        iputils \
        less \
        man \
        net-tools \
        net-tools-deprecated \
        python2 \
        python2-pip \
        sqlite3 \
        subversion \
        subversion-python \
        sudo \
        w3m \
        zile

RUN pip install Trac==1.0.10 Genshi

EXPOSE 80

COPY trac-container.conf /etc/apache2/conf.d/trac-container.conf

RUN a2enmod mod_status

COPY docker-init.sh /docker-init.sh
RUN chmod +x /docker-init.sh
ENTRYPOINT ["/docker-init.sh"]


