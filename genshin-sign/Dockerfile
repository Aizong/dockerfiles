FROM python:3-alpine
ENV CRON_SIGNIN='30 9 * * *'
ENV TZ=Asia/Shanghai

RUN apk --update add wget unzip && rm -rf /var/cache/apk/* \
    && wget -q --no-check-certificate https://github.com/sirodeneko/genshin-sign/archive/refs/heads/master.zip -O /tmp/master.zip \
    && unzip -j /tmp/master.zip -d /app && rm  /tmp/master.zip \
    && ls -ahl /app \
    && pip3 install -r /app/requirements.txt


WORKDIR /app

CMD ["python3", "./docker.py" ]