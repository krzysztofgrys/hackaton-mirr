FROM node:8.15.1-alpine



RUN apk add --update --no-cache \
    tzdata \
    bash \
    yarn \
    && mkdir /app

COPY ./js/start.sh /

RUN cp /usr/share/zoneinfo/Europe/Warsaw /etc/localtime \
    && echo "Europe/Warsaw" >  /etc/timezone

WORKDIR /app