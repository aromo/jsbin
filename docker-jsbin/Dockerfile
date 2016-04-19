FROM node:0.10

ENV AP /data/app
ENV SCPATH /etc/supervisor/conf.d

RUN apt-get -y update \
	&& apt-get -y install apt-utils supervisor \
	&& mkdir -p /var/log/supervisor \

# Supervisor Configuration
ADD ./supervisord/conf.d/* $SCPATH/

# Application Code
ADD src $AP/

WORKDIR $AP
ENV JSBIN_CONFIG $AP/config.default.json

RUN npm update -g \
	&& npm uninstall --save-optional zmq \
	&& npm i -S memcached@2.2.0 connect \
	&& npm i

#CMD ["supervisord", "-n"]

ENV JSBIN_CONFIG $AP/config.local.json

CMD ["node", "./bin/jsbin"]

EXPOSE 3000 5555
VOLUME $AP
