FROM nginx:alpine
MAINTAINER tkrplus

# TODO: ローカル用、本番運用では除去
RUN apk --update add openssl

RUN openssl genrsa 2048 > server.key \
  && openssl req -new -key server.key -subj "/C=JP/ST=Tokyo/L=Chuo-ku/O=RMP Inc./OU=web/CN=localhost" > server.csr \
  && openssl x509 -in server.csr -days 3650 -req -signkey server.key > server.crt \
  && cp server.crt /etc/nginx/server.crt \
  && cp server.key /etc/nginx/server.key \
  && chmod 400 /etc/nginx/server.key
