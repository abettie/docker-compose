FROM mysql:8.0.40-debian

COPY mysql/my.cnf /etc/mysql/conf.d/my.cnf

# apt高速化
RUN sed -i -e 's|deb.debian.org/debian|ftp.jp.debian.org/debian|g' /etc/apt/sources.list.d/debian.sources
RUN sed -i -e 's|ftp.jp.debian.org/debian-security|deb.debian.org/debian-security|g' /etc/apt/sources.list.d/debian.sources

# 日本語環境を追加
RUN apt-get update \
    && apt-get install -y locales \
    && sed -i -E 's/# (ja_JP.UTF-8)/\1/' /etc/locale.gen \
    && locale-gen \
    && update-locale LANG=ja_JP.UTF-8 \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
ENV LC_ALL ja_JP.UTF-8
