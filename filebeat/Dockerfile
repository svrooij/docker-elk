ARG ELK_VERSION

# https://github.com/elastic/kibana-docker
FROM docker.elastic.co/beats/filebeat-oss:${ELK_VERSION}

# Default variables
ENV LOGSTASH_HOST=logstash
ENV LOGSTASH_PORT=5000
ENV SHIPPER_NAME=filebeat-docker

# Copy filebeat config
COPY ./config/filebeat.yml /usr/share/filebeat/filebeat.yml

# Copy and set entrypoint
COPY ./docker-entrypoint.sh /entrypoint.sh
RUN  chmod +x /entrypoint.sh

ENTRYPOINT  ["/entrypoint.sh"]
CMD ["start"]
