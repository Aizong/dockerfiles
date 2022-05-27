FROM python:3-alpine
ENV CRON_SIGNIN='30 9 * * *'
ENV TZ=Asia/Shanghai

RUN apk --update add wget unzip  \
    && wget -q --no-cache --no-check-certificate https://github.com/sirodeneko/genshin-sign/archive/refs/heads/master.zip -O /tmp/master.zip \
    && unzip -o /tmp/master.zip -d /app && rm  /tmp/master.zip \
    && mv /app/genshin-sign-master/* /app && rm -rf /app/genshin-sign-master \
    && pip3 install -r /app/requirements.txt \
    && apk del wget unzip \
    && rm /var/cache/apk/*


WORKDIR /app

CMD ["python3", "./docker.py" ]