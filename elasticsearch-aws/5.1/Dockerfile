FROM elasticsearch:5.1
MAINTAINER ElasticM2M <elasticm2m@gmail.com>

WORKDIR /usr/share/elasticsearch

RUN bin/elasticsearch-plugin install --batch discovery-ec2
RUN bin/elasticsearch-plugin install --batch repository-s3

COPY docker-entrypoint.sh /docker-entrypoint.sh