# Workshop 23-11
## Starten met opbouwen
Docker @ Azure
- Maak VM
- Fix DNS
- Installeer Docker en docker-compose
```bash
sudo apt update
sudo apt dist-upgrade
sudo apt install docker.io docker-compose
sudo usermod -a -G docker Eric
sudo mkdir -p /opt/docker
sudo chown Eric /opt/docker
cd /opt/docker
git clone git@github.com:DITCOnsultants/Docker-workshop.git
cd Docker-workshop/
git checkout Workshop-23-11 
```

## Basis zonder traefik
- nginx op poort 8080 en 8081
```bash
cd No-Traefik/
docker-compose up
```

## Traefik basis
- Traefik ervoor om single point of entry
- Wat doet/kan Traefik: [Dashboard](http://az.frotmail.nl:8080)

## SSL / Letsencrypt / ... ?
- Traefik SSL
  - [webserver1](https://web1.az.frotmail.nl)
  - [webserver2](https://web2.az.frotmail.nl)

## Traefik in Kubernetes
- Folkert

## File configuration provider
- Andere hosts


# Extra A: Middleware
- Rewriting
- HTTP Auth (basic)
- Authelia
- SNI / eSNI / ECH (??)

# Extra B: T-shoot
- Logging
- API
- Dashboard

# Extra C: Health probes
- Load balancing (nu echt)
