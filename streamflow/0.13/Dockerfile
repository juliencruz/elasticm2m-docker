FROM elasticm2m/java:8
MAINTAINER ElasticM2M <elasticm2m@gmail.com>

# Download and unpack the Streamflow distribution
RUN wget -qO- https://github.com/lmco/streamflow/releases/download/0.13.0/streamflow-0.13.0.tar.gz | tar xvz -C /opt
RUN ln -s /opt/streamflow-0.13.0 /opt/streamflow

COPY configure-nimbus.sh /usr/bin/configure-nimbus.sh
COPY configure-elasticsearch.sh /usr/bin/configure-elasticsearch.sh
COPY streamflow.yml /opt/streamflow/conf/streamflow.yml

WORKDIR /opt/streamflow
ENV STREAMFLOW_HOME /opt/streamflow

VOLUME ["/opt/streamflow/data", "/opt/streamflow/temp"]

EXPOSE 8080

CMD /usr/bin/configure-nimbus.sh \
    && /usr/bin/configure-elasticsearch.sh \
    && /opt/streamflow/bin/streamflow.sh
