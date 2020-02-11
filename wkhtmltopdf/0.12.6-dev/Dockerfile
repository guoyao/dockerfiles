FROM guoyao/centos-node-git:centos7-node10

RUN yum install -y fontconfig freetype libX11 libXext libXrender libjpeg libpng openssl xorg-x11-fonts-75dpi xorg-x11-fonts-Type1 \
    && wget https://builds.wkhtmltopdf.org/0.12.6-dev/wkhtmltox-0.12.6-0.20180618.3.dev.e6d6f54.centos7.x86_64.rpm \
    && rpm -i wkhtmltox-0.12.6-0.20180618.3.dev.e6d6f54.centos7.x86_64.rpm \
    && rm -f wkhtmltox-0.12.6-0.20180618.3.dev.e6d6f54.centos7.x86_64.rpm

RUN curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py && python get-pip.py && rm -f get-pip.py

RUN pip install PrettyTable

RUN yum install -y kde-l10n-Chinese glibc-common \
    && localedef -c -f UTF-8 -i zh_CN zh_CN.utf8 \
    && export LANG=zh_CN.UTF-8 \
    && echo "export LANG=zh_CN.UTF-8" >> /etc/locale.conf \
    && yum groupinstall Fonts -y

ENV LANG zh_CN.UTF-8
ENV LC_ALL zh_CN.UTF-8

ENTRYPOINT ["wkhtmltopdf"]
