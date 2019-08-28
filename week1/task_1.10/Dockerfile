FROM node

WORKDIR /app

COPY . /app

RUN npm install

EXPOSE 5000

CMD API_URL=http://localhost:8000 npm start 
