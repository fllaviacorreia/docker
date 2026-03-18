FROM eclipse-temurin:17-jdk

ARG ANT_VERSION=1.10.13

RUN apt-get update \
  && apt-get install -y --no-install-recommends curl ca-certificates tar \
  && rm -rf /var/lib/apt/lists/*

ENV ANT_HOME=/opt/ant
ENV PATH="${ANT_HOME}/bin:${PATH}"

RUN mkdir -p "${ANT_HOME}" \
  && curl -fsSL --retry 5 -o /tmp/ant.tar.gz \
    "https://archive.apache.org/dist/ant/binaries/apache-ant-${ANT_VERSION}-bin.tar.gz" \
  && tar -xzf /tmp/ant.tar.gz --strip-components=1 -C "${ANT_HOME}" \
  && rm -f /tmp/ant.tar.gz

WORKDIR /work
CMD ["tail","-f","/dev/null"]
