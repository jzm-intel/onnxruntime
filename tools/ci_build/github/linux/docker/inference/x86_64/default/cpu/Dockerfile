# Copyright (c) Microsoft Corporation. All rights reserved.
# Licensed under the MIT License.

# This file is used by Zip-Nuget Packaging NoContribOps Pipeline,Zip-Nuget-Java Packaging Pipeline
FROM onnxruntimebuildcache.azurecr.io/internal/azureml/onnxruntime/build/cpu_x64_ubi8_gcc12_dotnet:20241120.3

ENV PATH=/usr/lib/jvm/msopenjdk-17/bin:/opt/rh/gcc-toolset-12/root/usr/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
ENV LANG=en_US.UTF-8
ENV LC_ALL=en_US.UTF-8

ADD scripts /tmp/scripts
RUN cd /tmp/scripts && /tmp/scripts/install_deps.sh && rm -rf /tmp/scripts

ARG BUILD_UID=1001
ARG BUILD_USER=onnxruntimedev
RUN adduser --uid $BUILD_UID $BUILD_USER
WORKDIR /home/$BUILD_USER
USER $BUILD_USER
