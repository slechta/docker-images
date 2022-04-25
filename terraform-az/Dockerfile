FROM registry.gitlab.com/gitlab-org/terraform-images/releases/terraform:1.0.3
ARG VERSION=azcopy_linux_amd64_10.14.1

RUN apk --update add --virtual build-dependencies --no-cache wget tar 
RUN apk --update add libc6-compat ca-certificates

RUN wget -O azcopyv10.tar https://aka.ms/downloadazcopy-v10-linux && \
    tar -xf azcopyv10.tar && \
    mkdir /app && \
    mv ${VERSION}/azcopy /sbin/azcopy && \
    rm -rf azcopy* && \
    apk del build-dependencies

