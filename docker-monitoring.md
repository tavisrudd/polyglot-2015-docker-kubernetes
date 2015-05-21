# Logging

docker logs & json-file default prior to 1.6

Log driver support in 1.6
```sh
docker run --rm --log-driver=syslog ubuntu seq 20
```

# Docker events



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
