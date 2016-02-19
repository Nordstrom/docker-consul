FROM nordstrom/consul-agent:0.6

ADD config/server.json /config/server.json

ENTRYPOINT ["/bin/consul", "agent", "-config-dir=/config", "-server", "-ui"]
