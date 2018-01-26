# cardano-daedalus-docker

Note this is all work in progress. Ideally just have a look at the Dockerfiles to see
how I setup Cardano and Deadalus on my Ubuntu machine. 

## How to run Cardano ($ADA) Daedalus wallet on Linux
### Requirements
- [Docker](https://docs.docker.com/engine/installation/)
- [Docker Compose](https://docs.docker.com/compose/install/)

### Build cardano-sl and Daedalus images
```
git clone https://github.com/hcvst/cardano-daedalus-docker.git
cd cardano-daedalus-docker
docker-compose build
```

### Startup
To clean up the wallet database lock file, allow local X11 connections and start the containers,
you can simply execute the startup script:
```
./start-daedalus
```

### Prebuilt images
- https://hub.docker.com/r/hcvst/cardano-sl-with-daedalus-wallet/ - all in one Ubuntu build
- https://hub.docker.com/r/hcvst/cardano-daedalus/ - Ubuntu based image of wallet
- https://hub.docker.com/r/hcvst/cardano-sl/ - Ubuntu based image of cardano-sl
- https://hub.docker.com/r/hcvst/cardano-sl-nix/ - nixos/nix based image of cardano-sl

Please note that these Docker images are quite big and will
mostly become absolete once the Daedalus wallet for Linux is released.

Please check: https://daedaluswallet.io.

## Help
If you have a question, please PM me (@hcvst) here https://cardano.rocket.chat or on Telegram (or https://gitter.im/daedalus-wallet-on-docker/Lobby).
This was tested with the following docker host systems:
- Arch
- Ubuntu 16.04

If you would like to help:
- The images are big. I initially tried alpine but got stuck (perhaps one can use nixOS directly?) Update: I have added `cardano-sl-nix`
- Are for the `daedalus-ds` build both `nix-builds` in the `Dockerfile` required or would the second suffice? Update: It seems to be enough to build the release only as per the nix image.
