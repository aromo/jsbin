FROM node:0.10

ENV AP /data/pennyworth

RUN apt-get -y update

ADD src $AP/

WORKDIR $AP

RUN /bin/bash bootstrap.sh

ENTRYPOINT ["bin/entrypoint"]

VOLUME $AP
