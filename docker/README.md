# Requirements

- Virtualbox
- Docker
- Docker-Compose
- Docker-Machine

# How to use

```
cp .env.dist .env
cp settings.json.dist settings.json
```

```
MACHINE=BigBuyAPI

docker-machine create \
    --driver=virtualbox \
    --virtualbox-cpu-count 2 \
    --virtualbox-disk-size 10000 \
    --virtualbox-memory 1024 \
    --virtualbox-share-folder "${HOME}:${HOME}" \
    "${MACHINE}"

MACHINE_PATH="${HOME}/.docker/machine/machines/${MACHINE}"

docker context create $MACHINE \
    --docker "host=tcp://$(docker-machine ip $MACHINE):2376,ca=${MACHINE_PATH}/ca.pem,cert=${MACHINE_PATH}/cert.pem,key=${MACHINE_PATH}/key.pem"

IP="$(docker-machine ip $MACHINE)"

docker context use $MACHINE
```

Add IP to .env file.

```
docker-compose up -d --build
```

Open `https://{IP}` in your browser.
