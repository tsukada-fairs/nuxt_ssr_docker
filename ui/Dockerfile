# 軽量らしいのでOSは、Alpine Linuxを選択
# https://hub.docker.com/_/node/
FROM node:12.18-alpine
 
# 環境変数
ENV LANG C.UTF-8
ENV TZ Asia/Tokyo
ENV APP_HOME /app
ENV PATH ${APP_HOME}/node_modules/.bin:$PATH
ENV HOST 0.0.0.0
ENV PORT 3000
 
WORKDIR ${APP_HOME}
ADD ui ${APP_HOME}

RUN apk update \
    && apk upgrade \
    # && yarn global add @vue/cli \
    # && yarn install \
    && rm -rf /var/cache/apk/*
 
EXPOSE 3000
 
CMD ["yarn", "dev"]