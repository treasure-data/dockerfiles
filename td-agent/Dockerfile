FROM base

MAINTAINER Treasure Data, Inc "https://github.com/treasure-data"

RUN apt-get install -y --force-yes curl
RUN curl -L http://toolbelt.treasuredata.com/sh/install-ubuntu-precise.sh | sh

RUN sed -i 's/ulimit/# ulimit/g' /etc/init.d/td-agent
RUN echo "ulimit -n 8192" >> /etc/default/td-agent

EXPOSE 8888
EXPOSE 24224

CMD ["/etc/init.d/td-agent", "start"]
