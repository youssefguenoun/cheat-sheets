
### List Services
``curl http://172.17.4.101:8500/v1/catalog/services``

``
{
    "consul": [],
    "fabio": [],
    "hello-world": [
        "urlprefix-hello-world.service/"
    ],
    "nomad": [
        "http",
        "rpc",
        "serf"
    ],
    "nomad-client": [
        "http"
    ]
}
``

### Deregister a service
``curl -XPUT 127.0.0.1:8500/v1/agent/service/deregister/<service-name>``

### Follow the logs of a running Consul agent
``consul monitor -log-level trace``

https://www.consul.io/docs/commands/monitor.html

### Healthcheck a service
``curl -s -S 127.0.0.1:8500/v1/health/service/account-service | jq .``

