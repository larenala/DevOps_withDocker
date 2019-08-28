FROM node

WORKDIR /

COPY . /

RUN npm install

RUN npm audit fix

EXPOSE 8000

CMD FRONT_URL=http://localhost:5000  npm start
