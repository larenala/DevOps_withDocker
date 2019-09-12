FROM node:alpine

RUN adduser --disabled-password app

WORKDIR /

COPY --chown=app:app . /

RUN npm install && \
    npm audit fix

USER app

EXPOSE 8000

CMD FRONT_URL=http://localhost:5000 npm start 
