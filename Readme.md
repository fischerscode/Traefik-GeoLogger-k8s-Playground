**NOT PRODUCTION READY**

This repos is my playground for testing [Traefik-GeoLogger](https://github.com/fischerscode/Traefik-GeoLogger) in kuberntes/minikube.

It might be a nice reference when adding [Traefik-GeoLogger](https://github.com/fischerscode/Traefik-GeoLogger) to a kubernetes cluster. A more production like configuration can be found [here](https://github.com/fischerscode/my-k3s/tree/master/infrastructure/base/traefik).

The private docker images of `fischerscode/traefik-geologger-city` are equal to the ones in [fischerscode/traefik-geologger](https://hub.docker.com/r/fischerscode/traefik-geologger) but contain the [GeoLite Database](https://dev.maxmind.com/geoip?lang=en). They are build using [this](https://github.com/fischerscode/Traefik-GeoLogger/blob/master/Dockerfile.database) dockerfile.


For testing the log rotation, I use this command. Executed in the traefik container, it writes 1MB of nonsense in `/var/log/access.log`.
```
< /dev/urandom tr -dc _A-Z-a-z-0-9 | head -c${1:-1048577} >> /var/log/access.log
```