FROM alpine:3.19
RUN apk add --no-cache nginx
COPY nginx.conf /etc/nginx/nginx.conf
RUN nginx -t
