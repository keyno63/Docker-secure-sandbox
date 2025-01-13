


secretを有効にしてdocker build
```
docker build \
  --ssh default \
  --secret id=secure_file,src=./config/secure_file \
  -f docker/Dockerfile -t docker-secure-sandbox:v0.0 .
```

有効にせずdocker build
```
docker build -f docker/Dockerfile -t docker-secure-sandbox:v0.0 .
```
