# use this empty Dockerfile to build your assignment

# NOTE: The instructions are now in the README.md file in this directory.
# should be using FROM, RUN, WORKDIR, COPY, EXPOSE, and CMD commands

FROM node:6-alpine

EXPOSE 3000

RUN  apk add --no-cache tini

RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

COPY package.json package.json

RUN npm install && npm cache clean --force

COPY . .

CMD [ "/sbin/tini", "--", "node" "./bin/www" ]