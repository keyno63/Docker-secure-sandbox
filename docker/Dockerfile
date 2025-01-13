FROM ubuntu:latest

WORKDIR /app
COPY . /app/
RUN apt update \
    && apt-get install git golang-go -y \
    && git config --global "url.git@github.com:.insteadOf" "https://github.com/"
RUN --mount=type=ssh \
    --mount=type=secret,id=config,target=/root/.ssh/config \
    --mount=type=secret,id=hosts,target=/root/.ssh/known_hosts \
    go mod vendor
