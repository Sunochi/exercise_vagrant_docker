FROM node

MAINTAINER sunochi

ADD app/package.json /tmp/package.json
RUN cd /tmp && npm install --production

RUN mkdir -p /opt/app && cp -a /tmp/node_modules /opt/app/

ENV NODE_ENV=production

RUN npm install pm2 -g

COPY app/ /opt/app/.

RUN rm  /opt/app/.jscsrc
RUN rm  /opt/app/.jshintrc

EXPOSE 7000

# Run app
CMD ["pm2-docker", "/opt/app/src/index.js"]
