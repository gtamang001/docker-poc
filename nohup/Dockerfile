FROM debian:latest
RUN addgroup usergroup
RUN adduser appuser
RUN usermod -g usergroup appuser
RUN chmod g+wx /var/log
RUN apt-get update && apt-get install -y supervisor procps
RUN mkdir -p /var/log/supervisor
COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf
WORKDIR /home
COPY test.sh test.sh
RUN chmod +x test.sh

CMD ["/usr/bin/supervisord"]