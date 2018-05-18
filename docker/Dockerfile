FROM docker.elastic.co/elasticsearch/elasticsearch:5.6.8

MAINTAINER https://github.com/cesargomezvela

# Set environment variables defaults
ENV ES_JAVA_OPTS "-Xms512m -Xmx512m"
ENV CLUSTER_NAME elasticsearch-default
ENV NODE_MASTER true
ENV NODE_DATA true
ENV NODE_INGEST true
ENV HTTP_ENABLE true
ENV NETWORK_HOST _site_
ENV HTTP_CORS_ENABLE true
ENV HTTP_CORS_ALLOW_ORIGIN *
ENV NUMBER_OF_MASTERS 1
ENV MAX_LOCAL_STORAGE_NODES 1
ENV SHARD_ALLOCATION_AWARENESS ""
ENV SHARD_ALLOCATION_AWARENESS_ATTR ""
ENV REPO_LOCATIONS ""
# Kubernetes requires swap is turned off, so memory lock is redundant
ENV MEMORY_LOCK false
ENV LICENSE basic

# kubernetes
ENV DISCOVERY_SERVICE elasticsearch-discovery

# Copy configuration
COPY config /usr/share/elasticsearch/config

# Copy run script
COPY run.sh /

CMD ["/run.sh"]
