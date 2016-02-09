FROM nordstrom/baseimage-ubuntu:14.04

ENV CONSUL_VERSION 0.6.3
ENV CONSUL_SHA256 b0532c61fec4a4f6d130c893fd8954ec007a6ad93effbe283a39224ed237e250

ADD https://releases.hashicorp.com/consul/${CONSUL_VERSION}/consul_${CONSUL_VERSION}_linux_amd64.zip /tmp/consul.zip
RUN apt-get update -qy \
 && apt-get install -qy unzip \
 && echo "${CONSUL_SHA256}  /tmp/consul.zip" > /tmp/consul.sha256 \
 && sha256sum -c /tmp/consul.sha256
RUN cd /bin \
 && unzip /tmp/consul.zip \
 && chmod +x /bin/consul \
 && rm /tmp/consul.zip

ENTRYPOINT ["/bin/consul"]
