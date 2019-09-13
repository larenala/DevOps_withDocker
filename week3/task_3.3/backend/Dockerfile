FROM ubuntu:16.04

RUN useradd -m app

WORKDIR /

COPY --chown=app:app . /

RUN apt-get update && apt-get install -y curl gnupg  && \
    curl -sL https://deb.nodesource.com/setup_11.x  | bash - && \
    apt-get -y install nodejs && \
    npm install &&  npm audit fix && \
    apt-get purge -y --auto-remove curl && \
    rm -rf /var/lib/apt/lists/*

USER app

EXPOSE 8000

CMD FRONT_URL=http://localhost:5000 npm start 
