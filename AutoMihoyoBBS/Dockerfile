FROM python:3-alpine
ENV CRON_SIGNIN='30 9 * * *'
ENV TZ=Asia/Shanghai

ARG VER=20220513

RUN apk --update add wget unzip  \
    && wget -q --no-cache --no-check-certificate https://github.com/Womsxd/AutoMihoyoBBS/archive/refs/heads/master.zip -O /tmp/master.zip \
    && unzip -j /tmp/master.zip -d /app && rm  /tmp/master.zip \
    && ls -ahl /app \
    && pip3 install -r /app/requirements.txt \
    && apk del wget unzip \
    && rm /var/cache/apk/*


WORKDIR /app

CMD ["python3", "./docker.py" ]