


secretを有効にしてdocker build
```
docker build \
  --ssh default \
  --secret id=config,src=${HOME}/ssh_config \
  --secret id=hosts,src=${HOME}/known_hosts \
  -f docker/Dockerfile -t docker-secure-sandbox:v0.0 .
```

有効にせずdocker build
```
docker build -f docker/Dockerfile -t docker-secure-sandbox:v0.0 .
```
