ARG ELK_VERSION

# https://github.com/elastic/beats/blob/master/filebeat/
FROM docker.elastic.co/beats/filebeat-oss:${ELK_VERSION}

COPY ./config/filebeat.yml /usr/share/filebeat/filebeat.yml
USER root
# Create a directory to map volume with all docker log files
RUN mkdir /usr/share/filebeat/dockerlogs && \
    chown -R root /usr/share/filebeat/ && \
    chmod -R go-w /usr/share/filebeat/