
```
docker-compose build code
docker-compose up -d
```

```
docker context create BigBuyAPI \
    --docker "host=ssh://127.0.0.1:2222,key=${PWD}/.docker/machine/machines/$MACHINE/key.pem"
```
