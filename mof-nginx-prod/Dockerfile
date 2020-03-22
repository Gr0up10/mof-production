FROM nginx:1-alpine
RUN apk update
RUN apk add certbot certbot-nginx
COPY nginx.conf /etc/nginx/nginx.conf
COPY fullchain.pem /etc/certs/fullchain.pem
COPY key.pem /etc/certs/key.pem
RUN echo "0 0,12 * * * root python -c 'import random; import time; time.sleep(random.random() * 3600)' && certbot renew -q" | tee -a /etc/crontab > /dev/null
