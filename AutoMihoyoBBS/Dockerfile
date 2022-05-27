FROM python:3-alpine
ENV CRON_SIGNIN='30 9 * * *'
ENV TZ=Asia/Shanghai

ARG VER=20220513

RUN apk --update add tzdata wget unzip  \
    && wget -q --no-cache --no-check-certificate https://github.com/Womsxd/AutoMihoyoBBS/archive/refs/heads/master.zip -O /tmp/master.zip \
    && rm -rf /var/app  \
    && unzip -o /tmp/master.zip -d /var/app && rm  /tmp/master.zip \
    && mv /var/app/AutoMihoyoBBS-master/* /var/app && rm -rf /var/app/AutoMihoyoBBS-master \
    && pip3 install -r /var/app/requirements.txt \
    && apk del wget unzip \
    && rm -rf /var/cache/apk/*


WORKDIR /var/app

CMD ["python3", "./docker.py" ]