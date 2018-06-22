FROM ubuntu:16.04

# if this use for production vps
#RUN groupadd kenji
#RUN useradd -u 1000 -g kenji kenji

WORKDIR /var/www
RUN apt-get update && apt-get install -my wget gnupg curl

# タイムゾーンの変更
ENV TZ Asia/Tokyo
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# 言語設定
RUN apt-get install -y locales
RUN locale-gen ja_JP.UTF-8
RUN apt-get install -y language-pack-ja
RUN locale-gen en_US.UTF-8
ENV LANG=C.UTF-8
ENV LANGUAGE=en_US:en


#nodejs
RUN curl -sL https://deb.nodesource.com/setup_8.x | bash - \
    && apt-get update \
    && apt-get install -y nodejs

# vue-cli
RUN npm install -g vue-cli


# if this use for production vps
#USER kenji
#RUN mkdir ~/.npm-global
#RUN npm config set prefix '~/.npm-global'
#RUN echo export PATH=~/.npm-global/bin:$PATH >> ~/.profile
#RUN ls -l ~/.profile
#RUN . ~/.profile # for debian, if use ubuntu or centos use comand [source ~/.profile]
