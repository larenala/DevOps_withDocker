FROM ubuntu:16.04

WORKDIR /app
COPY . /app

RUN apt-get update && apt-get install -y curl wget 
CMD ["./script.sh"]



