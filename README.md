# cardano-daedalus-docker

## How to run Cardano ($ADA) Daedalus wallet on Linux
Note this is all work in progress. Ideally just have a look at the Dockerfiles to see
how I setup Cardano and Deadalus on my Ubuntu machine. 

They are built automatically by Docker hub. Please see:
- https://hub.docker.com/r/hcvst/cardano-sl-with-daedalus-wallet/ - all in one Ubuntu build
- https://hub.docker.com/r/hcvst/cardano-daedalus/ - Ubuntu based image of wallet
- https://hub.docker.com/r/hcvst/cardano-sl/ - Ubuntu based image of cardano-sl
- https://hub.docker.com/r/hcvst/cardano-sl-nix/ - nixos/nix based image of cardano-sl

Please note that these Docker images are quite big and will
mostly become absolete once the Daedalus wallet for Linux is released.

Please check: https://daedaluswallet.io.

## Manual start
- Initial start: `docker run -d --name=cardano  -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY hcvst/cardano-sl-with-daedalus-wallet`
- Stop: `docker stop cardano`
- Start: `docker start cardano`(This does not work so once you stop this image you loose the synced blockchain!)

## Using Docker Compose
- [Install Docker Compose](https://docs.docker.com/compose/install/)
- `git clone https://github.com/hcvst/cardano-daedalus-docker.git`  
- `cd cardano-daedalus-docker` 
- `docker-compose up`

## Help
If you have a question, please PM me (@hcvst) here https://cardano.rocket.chat. I have only tested this on an Ubuntu 16.04 docker host. 

If you would like to help ...:
- If have no idea whether this is safe. If not please log a ticket.
- The images are big. I initially tried alpine but got stuck (perhaps one can use nixOS directly?) Update: I have added `cardano-sl-nix`
- Are for the `daedalus-ds` build both `nix-builds` in the `Dockerfile` required or would the second suffice? Update: It seems to be enough to build the release only as per the nix image.
- The blockchain should probably be stored in a docker volume
- I am not happy yet with `docker-compose.yml` and its `network_mode` in particular nor the `X` volume, which oddly I didn't need to add for it to work. If you know docker compose please take a look.
