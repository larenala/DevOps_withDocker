FROM node:alpine

RUN adduser app --disabled-password

WORKDIR /

COPY --chown=app:app . /

RUN npm install

USER app

EXPOSE 5000

CMD API_URL=http://localhost:8000  npm start
