FROM ruby:latest

WORKDIR /app

COPY . /app

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash

RUN apt-get update && apt install -y nodejs 

RUN bundle update --ruby

RUN bundle install

RUN rails db:migrate

EXPOSE 3000

CMD rails s
