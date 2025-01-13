FROM ubuntu:latest

WORKDIR /app
COPY . /app/
RUN apt update \
    && apt-get install git golang-go -y \
    && git config --global "url.git@github.com:.insteadOf" "https://github.com/"
RUN --mount=type=ssh \
    --mount=type=secret,id=secure_file,target=/app/secure_file \
    export SECURE_VALUE=$(cat /app/secure_file) \
    && echo "SECURE_VALUE=$SECURE_VALUE" >> /etc/environment
RUN go mod vendor
