# cardano-daedalus-docker
The Dockerfiles for the Daedalus and Cardano SL builds are located
in the `daedalus` and `cardano-sl` directories.

They are build automatically by Docker hub. Please see:
- https://hub.docker.com/r/hcvst/cardano-daedalus/
- https://hub.docker.com/r/hcvst/cardano-sl/

The easiest way to start a node and a wallet is to use Docker Compose.

Please note that these Docker images are quite big and will
mostly become absolete once the Daedalus wallet for Linux is released.

Please check: [https://daedaluswallet.io]().

## Using Docker Compose
*WIP* - I haven't written it yet
- [Install Docker Compose](https://docs.docker.com/compose/install/)
- `git clone https://github.com/hcvst/cardano-daedalus-docker.git`  
- `cd cardano-daedalus-docker` 
- `docker-compose up`

## Manual
- Daedalus on Ubuntu 16.04 - `docker run --rm -ti  -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=$DISPLAY -v /tmp/.docker.xauth:/tmp/.docker.xauth  -e XAUHORITY=/tmp/.docker.xauth --net=host hcvst/cardano-daedalus`
- Cardano Node - Docker hub build wasn't ready when I wrote this but you will need to expose port 8090

## Help
- If have no idea whether this is safe. If not please log a ticket.
- The images are big. I initially tried alpine but got stuck (perhaps one can use nixOS directly?)
- Are for the `daedalus-ds` build both `nix-builds` in the `Dockerfile` required or would the second suffice? 
