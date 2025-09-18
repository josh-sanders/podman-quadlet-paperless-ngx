# Paperless-ngx Quadlet

This is setup to run as root. Postgres is happy, NFS is happy, the consume worker is happy. 

## Prerequisites

- nfs server needs to be set to norootsquash. In Napp-IT this is rw=on,root=on.

## Pull container images

podman pull docker.io/apache/tika:latest docker.io/library/postgres:17 ghcr.io/paperless-ngx/paperless-ngx:2.0.0 docker.io/library/redis:8 docker.io/gotenberg/gotenberg:8.20 ghcr.io/paperless-ngx/paperless-ngx:2.18

## Stow the quadlets
Assuming this file is located at `/home/josh/stow/paperless/` then run:

    # stow --no-folding --verbose --target=/ --dir=/home/josh/stow paperless

## Start paperless

    # systemctl daemon-reload
    # systemctl start paperless-ngx

## References and similar work

Thank you:

- [ChristophHannappel / PaperlessNGX-Quadlet](https://github.com/ChristophHannappel/PaperlessNGX-Quadlet)
- [travier / paperless-ngx-quadlets](https://github.com/travier/paperless-ngx-quadlets)
