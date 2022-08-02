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

FROM ubuntu

WORKDIR /opt/perf

RUN apt-get update && \
    apt-get install -y sudo vim dumb-init && \
    apt-get install -y wget curl && \
    apt-get clean all
RUN echo "alias ll='ls -al'" >> /etc/bash.bashrc && \
    echo "alias ..='cd ..'" >> /etc/bash.bashrc && \
    echo "alias ...='cd ../..'" >> /etc/bash.bashrc && \
    echo "alias tailf='tail -f'" >> /etc/bash.bashrc && \
    echo "set nu" >> /etc/vim/vimrc
