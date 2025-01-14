FROM nginx:stable-alpine3.20
COPY ./html /usr/share/nginx/html
EXPOSE 80
EXPOSE 443
RUN apk add apk-cron && apk add nano
CMD ["nginx", "-g", "daemon off;"]

ADD crontab.txt /crontab.txt
ADD script.sh /script.sh
COPY entry.sh /entry.sh
RUN chmod 755 /script.sh /entry.sh
RUN /usr/bin/crontab /crontab.txt

CMD ["/start.sh"]
