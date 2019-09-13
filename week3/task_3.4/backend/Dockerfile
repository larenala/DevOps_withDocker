FROM node:alpine

RUN adduser -D app

WORKDIR /app

COPY --chown=app:app  . /app

RUN npm install && npm audit fix

EXPOSE 8000

CMD FRONT_URL=http://localhost:5000  npm start
