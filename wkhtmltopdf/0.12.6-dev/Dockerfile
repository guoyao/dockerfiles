FROM guoyao/centos-node-git:centos7-node10

RUN yum install -y fontconfig freetype libX11 libXext libXrender libjpeg libpng openssl xorg-x11-fonts-75dpi xorg-x11-fonts-Type1 \
    && wget https://builds.wkhtmltopdf.org/0.12.6-dev/wkhtmltox-0.12.6-0.20180618.3.dev.e6d6f54.centos7.x86_64.rpm \
    && rpm -i wkhtmltox-0.12.6-0.20180618.3.dev.e6d6f54.centos7.x86_64.rpm \
    && rm -f wkhtmltox-0.12.6-0.20180618.3.dev.e6d6f54.centos7.x86_64.rpm

ENTRYPOINT ["wkhtmltopdf"]