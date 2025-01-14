FROM nginx:stable-alpine3.20
COPY ./html /usr/share/nginx/html
EXPOSE 80
EXPOSE 443
RUN apk add apk-cron && apk add nano

ADD crontab.txt /crontab.txt
ADD script.sh /script.sh
COPY entry.sh /entry.sh
RUN chmod 755 /script.sh /entry.sh
RUN /usr/bin/crontab /crontab.txt

ADD start.sh /start.sh
RUN chmod +x /start.sh

CMD ["/usr/bin/bash", "/start.sh"]
