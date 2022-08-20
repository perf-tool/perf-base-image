#
# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements.  See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing,
# software distributed under the License is distributed on an
# "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
# KIND, either express or implied.  See the License for the
# specific language governing permissions and limitations
# under the License.
#

FROM perftool/base:latest

WORKDIR /opt/perf

ARG TARGETARCH

RUN apt-get update && \
    apt-get install -y openjdk-17-jdk unzip && \
    apt-get clean all && \
    wget https://downloads.apache.org/skywalking/java-agent/8.11.0/apache-skywalking-java-agent-8.11.0.tgz && \
    mkdir /opt/perf/skywalking-agent && \
    tar -xf apache-skywalking-java-agent-8.11.0.tgz -C skywalking-agent --strip-components 1 && \
    rm -rf apache-skywalking-java-agent-8.11.0.tgz && \
    wget https://github.com/alibaba/arthas/releases/download/arthas-all-3.6.4/arthas-bin.zip && \
    mkdir -p /opt/perf/arthas && \
    unzip arthas-bin.zip -d /opt/perf/arthas && \
    rm -rf arthas-bin.zip && \
    echo "alias arthas='java -jar /opt/perf/arthas/arthas-boot.jar'" >> /root/.bashrc

ENV JAVA_HOME /usr/lib/jvm/java-17-openjdk-$TARGETARCH
