FROM node:alpine
RUN apk --update add curl
RUN apk add --no-cache tini
# Tini is now available at /sbin/tini
EXPOSE 8080
ENTRYPOINT ["/sbin/tini", "--"]