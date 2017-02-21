# NAME:     discourse/discourse
# VERSION:  1.3.10
FROM discourse/base:1.3.10

MAINTAINER Sam Saffron "https://twitter.com/samsaffron"

# Discourse specific bits
RUN useradd discourse -s /bin/bash -m -U &&\
    mkdir -p /var/www &&\
    cd /var/www &&\
    git clone https://github.com/SumatoSoft/discourse.git &&\
    cd discourse &&\
    chown -R discourse:discourse /var/www/discourse &&\
    cd /var/www/discourse &&\
    sudo -u discourse bundle install --deployment \
         --without test --without development &&\
    find /var/www/discourse/vendor/bundle -name tmp -type d -exec rm -rf {} +

COPY vb_forum.map /etc/nginx/vb_forum.map
