FROM ruby:alpine3.7

COPY .ssh /root/.ssh

RUN apk add --update --no-cache openssh icu-dev build-base git cmake libxml2-dev libxslt-dev && \
    rm -rf /var/lib/apt/lists/* && \
    gem install gollum charlock_holmes org-ruby github-markdown \
    omnigollum omniauth-github

RUN git clone git@gitlab.com:tkrplus/niwalab-wiki.git /wiki && \
    touch /etc/periodic/15min/gollumpush && \
    echo -e "#!/bin/sh\ncd /wiki && git push origin master" >> /etc/periodic/15min/gollumpush && \
    chmod a+x /etc/periodic/15min/gollumpush

WORKDIR /wiki

CMD crond && gollum -p 80 --config config.rb
