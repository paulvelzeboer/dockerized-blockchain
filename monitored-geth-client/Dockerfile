FROM ethereum/client-go:v1.6.5

LABEL maintainer="paulvelzeboer@gmail.com"

RUN apk update &&\
    apk add git nodejs bash perl tar

COPY eth-net-intelligence-api.tar.gz /root/eth-net-intelligence-api.tar.gz
COPY hello.js /tmp/hello.js
COPY coin.js /tmp/coin.js
RUN cd /root &&\
    tar xvzf /root/eth-net-intelligence-api.tar.gz  &&\
    cd eth-net-intelligence-api &&\
    npm install &&\
    npm install -g pm2

ADD start.sh /root/start.sh
ADD app.json /root/eth-net-intelligence-api/app.json
RUN chmod +x /root/start.sh

ENTRYPOINT /root/start.sh
