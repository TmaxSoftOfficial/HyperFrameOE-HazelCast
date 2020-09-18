FROM openjdk:8

# Versions of Hazelcast and Hazelcast plugins
ARG HZ_VERSION="4.0.1"
ARG CACHE_API_VERSION="1.1.0"

# Build constants
ARG HZ_HOME="/opt/hazelcast"

ARG HZ_JAR="hazelcast-all-${HZ_VERSION}.jar"
ARG CACHE_API_JAR="cache-api-${CACHE_API_VERSION}.jar"

ARG JAR_URL="https://github.com/TmaxSoftOfficial/HyperFrameOE-Hazelcast/raw/master"

# Runtime constants / variables
ENV HZ_HOME="${HZ_HOME}" \
    CLASSPATH_DEFAULT="${HZ_HOME}/*:${HZ_HOME}/lib/*:${JAVA_HOME}/lib/tools.jar" \
    JAVA_OPTS_DEFAULT="-Djava.net.preferIPv4Stack=true -Djava.util.logging.config.file=${HZ_HOME}/logging.properties -XX:MaxRAMPercentage=80.0 -XX:+UseParallelGC" \
    LOGGING_LEVEL="" \
    CLASSPATH="" \
    JAVA_OPTS=""

# Expose port
EXPOSE 5701

#COPY *.sh *.properties ${HZ_HOME}/
RUN apt-get install wget
RUN wget https://github.com/TmaxSoftOfficial/HyperFrameOE-Hazelcast/blob/master/hazelcast_4.0.1/logging.properties -P ${HZ_HOME}/
RUN wget https://github.com/TmaxSoftOfficial/HyperFrameOE-Hazelcast/blob/master/hazelcast_4.0.1/start-hazelcast.sh -P ${HZ_HOME}/ 

RUN echo "Installing Hazelcast" \
    && mkdir "${HZ_HOME}/lib" \
    && curl -sf -o ${HZ_HOME}/lib/${HZ_JAR} -L ${JAR_URL}/${HZ_JAR} \
    && echo "Installing JCache" \
    && curl -sf -o ${HZ_HOME}/lib/${CACHE_API_JAR} -L ${JAR_URL}/${CACHE_API_JAR} \
    && echo "Granting read permission to ${HZ_HOME}" \
    && chmod -R +r $HZ_HOME \
    && echo "Setting Pardot ID to 'docker'" \
    && echo 'hazelcastDownloadId=docker' > hazelcast-download.properties

WORKDIR ${HZ_HOME}

# Start Hazelcast server
CMD ["/opt/hazelcast/start-hazelcast.sh"]

