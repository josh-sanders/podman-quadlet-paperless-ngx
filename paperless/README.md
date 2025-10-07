# Paperless-ngx Quadlet

## Rootless

This is setup to run podamn root, but prevent the containers from running any processes as root. This keeps the Postgres container happy, NFS just works, and we can use ports 80 and 443.

## Prerequisites

### NFS

- nfs server needs to be set to norootsquash. In Napp-IT this is rw=on,root=on.

## Quickstart

### Pull container images

podman pull docker.io/apache/tika:latest docker.io/library/postgres:17 docker.io/library/redis:8 docker.io/gotenberg/gotenberg:8.20 ghcr.io/paperless-ngx/paperless-ngx:2.18

### Stow the quadlets

Assuming this file is located at `/home/josh/stow/paperless/` then run:

    # stow --no-folding --verbose --target=/ --dir=/home/josh/stow paperless

### Start paperless

    # systemctl daemon-reload
    # systemctl start paperless-pod

## Remote access

### Tunnel 

Both Pagekite and Cloudflare tunnel are included. Pagekite is free as in freedom, Cloudflare is free as in gratis. Both tunnels terminate on the reverse proxy. Of course you don't need to use a tunnel and can setup your router and DNS to land on caddy.

### Reverse proxy

Caddy is provided with the cloudflare addon so that it can setup TLS automagically, if you use cloudflare as your DNS.

## References and similar work

Thank you:

- [ChristophHannappel / PaperlessNGX-Quadlet](https://github.com/ChristophHannappel/PaperlessNGX-Quadlet)
- [travier / paperless-ngx-quadlets](https://github.com/travier/paperless-ngx-quadlets)
