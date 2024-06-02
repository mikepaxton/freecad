# FreeCad 

This guide will help you set up FreeCad using Docker Compose. Follow the steps below to configure your environment and get FreeCad up and running.

## Prerequisites

- Docker installed on your system.
- Docker Compose installed on your system.

## Docker Compose Setup
Source Documentation:  https://github.com/linuxserver/docker-freecad?tab=readme-ov-file
Review the source documentation for additional functions and features.
By default a freecad directory will be created in Admin's Document folder.  This can be changed to another location of your liking.
Change the Time Zone for your area by editing the TZ environment variable.

```yaml
services:
  freecad:
    security_opt:
      - seccomp:unconfined
    environment:
      - PUID=1001
      - PGID=1001
      - TZ=America/Los_Angeles
      - TITLE=FreeCad
    volumes:
      - /home/admin/Documents/freecad:/config
    ports:
      - 8150:3000
      - 8151:3001
    restart: unless-stopped
```

## Running Freecad

```sh
docker compose up -d
```


