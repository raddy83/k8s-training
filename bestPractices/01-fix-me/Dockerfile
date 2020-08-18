FROM ubuntu:latest

ENV LOG_FILE=/var/log/example/app.log

VOLUME [ "/var/log/example" ]

RUN mkdir -p "${LOG_FILE%/*}" \
  && echo "LOG FILE" >> ${LOG_FILE}

RUN apt-get update

RUN apt-get install -y --no-install-recommends \
  g++ \
  gcc \
  libc6-dev \
  make

RUN rm -rf /var/lib/apt/lists/*

ADD ./src/Makefile /var/lib/my-app/Makefile
ADD ./src/*.sh /opt/example/

WORKDIR /var/lib/my-app

ENTRYPOINT [ "/opt/example/entrypoint.sh" ]
CMD [ "make" ]