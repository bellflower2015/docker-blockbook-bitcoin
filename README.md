# docker-blockbook-bitcoin

Blockbook Dockerfile for Bitcoin

## Usage (directly from Docker Hub)

```
docker run \
    --hostname blockbook \
    -it \
    -v "$(PWD)/db:/blockbook/db" \
    -p 9130:9130 \
    -e RPC_USER=user \
    -e RPC_PASS=pass \
    -e RPC_HOST=127.0.0.1 \
    -e RPC_PORT=8332 \
    -e MQ_PORT=28332 \
    -e TZ=Asia/Tokyo \
    bellflower2015/blockbook-bitcoin
```

Blockbook config directory is `/blockbook/config` and database directory is `/blockbook/db`.

You can set environment variables `RPC_USER`, `RPC_PASS`, `RPC_HOST`, `RPC_PORT`, and `MQ_PORT`, and also set `TZ` to change timezone.

If you want to change hostname displayed, you can set it by `--hostname`.

## Build and run instructions

### Build image

Get source code and make docker image:

```
git clone https://github.com/bellflower2015/docker-blockbook-bitcoin.git
cd docker-blockbook-bitcoin
docker build -t blockbook-bitcoin .
```

Docker images are based on Debian 9 (Stretch).

### Run image

Boot from the built image as described below:

```
docker run [options] blockbook-bitcoin
```
