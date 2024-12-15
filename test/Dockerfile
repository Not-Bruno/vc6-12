FROM ubuntu

CMD apt update \
    apt install -y hugo git

CMD mkdir /var/www/html/

WORKDIR /var/www/html/

CMD hugo new site documentations

WORKDIR documentations

CMD git submodule add -f https://github.com/panr/hugo-theme-terminal.git themes/terminal

COPY ./vault/sample_hugo.toml ./hugo.toml
COPY ./vault/docs/*  ./content

CMD hugo server -t terminal