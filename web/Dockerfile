FROM httpd:2.4-alpine
 
RUN apk --no-cache add tzdata && \
    cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime && \
    apk del tzdata

EXPOSE 80 8080