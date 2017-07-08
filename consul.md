
### Deregister a service
``curl -XPUT 127.0.0.1:8500/v1/agent/service/deregister/<service-name>``

### Follow the logs of a running Consul agent
``consul monitor -log-level trace``

https://www.consul.io/docs/commands/monitor.html

### Healthcheck a service
``curl -s -S 127.0.0.1:8500/v1/health/service/account-service | jq .``

