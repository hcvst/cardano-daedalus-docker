# cardano-daedalus-docker
The Dockerfiles for the Daedalus and Cardano SL builds are located
in the `daedalus` and `cardano-sl` directories.

They are build automatically by Docker hub. Please see:
- [https://hub.docker.com/r/hcvst/cardano-daedalus/]()
- [https://hub.docker.com/r/hcvst/cardano-sl/]()

The easiest way to start a node and a wallet is to use Docker Compose.

Please note that these Docker images are quite big and will
mostly become absolete once the Daedalus wallet for Linux is released.

Please check: [https://daedaluswallet.io]().

## Using Docker Compose
- [https://docs.docker.com/compose/install/](Install Docker Compose)
- `git clone https://github.com/hcvst/cardano-daedalus-docker.git`  
- `cd cardano-daedalus-docker` 
- `docker-compose up`
