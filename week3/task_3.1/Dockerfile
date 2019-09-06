FROM node:alpine

WORKDIR /

COPY . /

RUN npm install && npm audit fix

EXPOSE 8000

CMD FRONT_URL=http://localhost:5000  npm start
