FROM ubuntu:16.04

ENV LC_ALL=C.UTF-8

RUN apt-get update && apt-get install -y \
    python3.5 python3-pip ffmpeg wget && \
    pip3 install -U  yle-dl && \
    chmod a+x /usr/local/bin/yle-dl && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /app

ENTRYPOINT ["/usr/local/bin/yle-dl"]
