FROM public.ecr.aws/nginx/nginx:stable-alpine

ARG NGINX_PORT=80
ARG HEALTH_CHECK_PATH=/health
ARG SERVICE_NAME=nginx

ENV NGINX_PORT=${NGINX_PORT}
ENV HEALTH_CHECK_PATH=${HEALTH_CHECK_PATH}
ENV SERVICE_NAME=${SERVICE_NAME}

COPY ./default.conf.template /etc/nginx/templates/default.conf.template

WORKDIR /usr/share/nginx/html

RUN curl -o master.zip -L https://codeload.github.com/nikolaym-commit/2048/zip/master
RUN unzip master.zip && mv 2048-master/* . && rm -rf 2048-master master.zip
