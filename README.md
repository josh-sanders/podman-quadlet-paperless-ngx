# README

## Prerequisites

- podman
- stow
- nfs-client

## Podman Quadlet

The majority of these packages contain Quadlet files for various services.

## GNU `stow`

The packages herein have been setup to be used with [GNU Stow](https://www.gnu.org/software/stow/).

## Cockpit

Install OpenSUSE MicroOS and add Cockpit after installation. If cockpit is included during installation it will also install cockpit-selinux and cockpit-storaged which I don't want.

    transactional-update pkg install -t pattern microos_cockpit
