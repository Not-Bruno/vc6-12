FROM php:8.2-apache

ENV PORT=80

RUN apt update && apt install -y git golang-go hugo

WORKDIR /var/www/html/

RUN hugo new site documentations

WORKDIR documentations

RUN git clone https://github.com/panr/hugo-theme-terminal.git themes/terminal

COPY ./vault/sample_hugo.toml ./hugo.toml
COPY ./vault/docs/*  ./content/

CMD ["sh", "-c", "hugo server -p $PORT -t terminal"]