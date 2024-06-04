FROM python:3.12.3-alpine3.18

RUN apk update && \
    apk add --no-cache pkgconfig mariadb-dev build-base && \
    rm -rf /var/cache/apk/*

WORKDIR /app
COPY ./app .
RUN pip install virtualenv
RUN virtualenv venv
RUN source venv/bin/activate

RUN chmod -R 777 /app
RUN pip install --no-cache-dir -r requirements.txt
CMD ["flask", "run", "--host=0.0.0.0"]