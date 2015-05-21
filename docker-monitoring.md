# Built-in Logging Options

docker logs & json-file default prior to 1.6

Log driver support in 1.6
```sh
docker run --rm --log-driver=syslog ubuntu seq 20
```

# Using the logstash ELK stack

See
http://kartar.net/2014/09/when-logstash-and-syslog-go-wrong/

http://untergeek.com/2012/10/11/using-rsyslog-to-send-pre-formatted-json-to-logstash/

# Docker events

# Docker stats

# cAdvisor

[https://github.com/google/cadvisor](https://github.com/google/cadvisor)

[https://github.com/google/cadvisor/blob/master/docs/api.md](https://github.com/google/cadvisor/blob/master/docs/api.md)

```sh
sudo docker run \
  --volume=/:/rootfs:ro \
  --volume=/var/run:/var/run:rw \
  --volume=/sys:/sys:ro \
  --volume=/var/lib/docker/:/var/lib/docker:ro \
  --publish=8080:8080 \
  --detach=true \
  --name=cadvisor \
    google/cadvisor:latest
```

# http://rancher.com/docker-monitoring-continued-prometheus-and-sysdig/

# resources
http://rancher.com/comparing-monitoring-options-for-docker-deployments/
