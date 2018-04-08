FROM node:alpine
MAINTAINER tkrplus

RUN apk add --update --no-cache git && \
    rm -rf /var/lib/apt/lists/* && \
    git clone https://github.com/tkrplus/niwalab-bot.git /niwalab-bot

WORKDIR /niwalab-bot

CMD ["bin/hubot", "--adapter", "slack"]
