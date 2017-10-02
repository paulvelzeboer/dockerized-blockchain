FROM node:7

LABEL maintainer="paulvelzeboer@gmail.com"

COPY eth-netstats.tar.gz /eth-netstats.tar.gz
RUN tar xvzf /eth-netstats.tar.gz
RUN cd /eth-netstats && npm install
RUN cd /eth-netstats && npm install -g grunt-cli
RUN cd /eth-netstats && grunt

WORKDIR /eth-netstats

EXPOSE 3000

CMD ["npm", "start"]
