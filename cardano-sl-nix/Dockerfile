FROM nixos/nix:1.11.14

RUN nix-env -ib git
RUN mkdir /etc/nix
RUN echo binary-caches = https://cache.nixos.org https://hydra.iohk.io > /etc/nix/nix.conf
RUN echo binary-caches-public-keys = hydra.iohk.io:f/Ea+s+dFdN+3Y/G+FDgSq+a5NEWhJGzdjvKNGv0/EQ= >> /etc/nix/nix.conf
RUN git clone https://github.com/input-output-hk/cardano-sl.git
WORKDIR /cardano-sl
RUN git checkout 1.1.0
RUN nix-build -A connectScripts.mainnetWallet -o connect-to-mainnet

EXPOSE 8090
CMD ./connect-to-mainnet
