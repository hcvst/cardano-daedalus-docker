FROM hcvst/cardano-sl

USER root
RUN apt-get update &&\
    apt-get install -y git curl build-essential libgtk2.0.0 libasound2 \
                       libnotify-bin libgconf-2-4 libnss3 libxss1 &&\
    curl -sL https://deb.nodesource.com/setup_6.x | bash &&\
    apt-get install -y nodejs
USER cardano
WORKDIR /home/cardano
RUN git clone https://github.com/input-output-hk/daedalus.git &&\
    cd daedalus &&\
    npm install && npm run-script package
RUN mkdir daedalus/tls/ca && cp daedalus/tls/ca.crt daedalus/tls/ca
ENTRYPOINT cd daedalus && npm start & cd cardano-sl && ./connect-to-mainnet
