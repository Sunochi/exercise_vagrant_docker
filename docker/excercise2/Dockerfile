From node

MAINTAINER Sunochi <sunouchicy@gmail.com>

RUN mkdir -p /opt/app
WORKDIR /opt/app

COPY package.json .
RUN npm install --quiet

VOLUME /opt/app/node_modules

COPY . .

EXPOSE 8080

