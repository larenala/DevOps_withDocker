FROM node:alpine

RUN adduser -D app

WORKDIR /app

COPY --chown=app:app  . /app

RUN npm install && npm audit fix

EXPOSE 5000

USER app

CMD API_URL=http://localhost:8000  npm start
