FROM ubuntu:16.04

ENV LC_ALL=C.UTF-8

WORKDIR /app

RUN apt-get update && apt-get install -y \
    python3-pip ffmpeg wget && \
    pip3 install -U  yle-dl && \
    chmod a+x /usr/local/bin/yle-dl && \
    apt-get purge -y --auto-remove python3-pip && \ 
    rm -rf /var/lib/apt/lists/*


ENTRYPOINT ["/usr/local/bin/yle-dl"]
