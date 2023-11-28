# README needs update :P


# De basis
Hoewel ik dit heel snel de basis noem zitten er toch al vrij veel zaken in die wellicht beter passen in een workshop voor gevorderden.

De reden waarom ik ze toch laat staan is omdat je ze waarschijnlijk vaak nodig hebt en dus onderdeel zouden moeten zijn van je basis kennis mocht je wat met Traefik willen doen.

# Een webserver
Zonder web content kan je niet zo gek veel doen met een loadbalancer/reverse proxy. Daarom starten we vanuit de docker-compose een nginx webservertje die een 2-tal statische HTML pagina's kan uitspugen, afhankelijk van het pad dat je aanroept.

# De loadbalancer
Vaak gebruiken we Traefik als een reverse proxy. Dit is eigenlijk gewoon een loadbalancer met vaak maar 1 'backend server' per dienst. Er valt dus niets te balanceren.

Later kom ik hier nog op terug. Als je immers een site hebt die onverhoopt een keer stuk gaat, waarom zou je dan geen 'sorry' pagina presenteren?

## Configuratie
De Traefik configuratie bestaat uit 2 delen, de statische config en de dynamische config.
Voor de statische configuratie heb je 3 opties:
* Als traefik.yml
* Als opstart parameters
* Als environment

Voor deze workshop gebruiken we de opstart parameters als statische config (via docker-compose) en laden we de Docker provider als input voor de dynamische configuratie.

```yaml
    command:
      - "--log.level=DEBUG"
      - "--accesslog=true"
      - "--api.insecure=true"
      - "--api.dashboard=true"
      - "--providers.docker=true"
      - "--providers.docker.exposedbydefault=false"
      - "--entryPoints.http.address=:80"
      - "--entryPoints.https.address=:443"
      - "--entryPoints.https.http.tls=true"
```

### Routers / Services

### Middlewares

## ACME / Letsencrypt
