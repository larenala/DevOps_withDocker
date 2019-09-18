FROM ubuntu:16.04 as build-stage

WORKDIR /usr/app

COPY . /usr/app

RUN apt-get update && apt-get install -y curl  && \
    curl -sL https://deb.nodesource.com/setup_11.x  | bash - && \
    apt-get -y install nodejs && \
    npm install &&  npm audit fix && \
    npm run build

FROM node:alpine

WORKDIR /usr/share

COPY --from=build-stage /usr/app/dist/ dist/

RUN npm install -g serve

EXPOSE 5000

CMD API_URL=http://localhost:8000 serve -s -l 5000 dist
