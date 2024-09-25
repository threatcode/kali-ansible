# Kali (Rolling) Ansible Test Image #

![Build](https://github.com/khulnasoft/docker-kali-ansible/workflows/Build/badge.svg?branch=master)
 [![Docker pulls](https://img.shields.io/docker/pulls/khulnasoft/docker-kali-ansible)](https://hub.docker.com/r/khulnasoft/docker-kali-ansible/)

Kali Linux (Rolling) Docker container for Ansible playbook and role testing.

## Tags ##

  - `latest`: Latest stable version of Ansible, with Python 3.x.

## How to Build ##

This image is built on Docker Hub automatically any time the upstream OS container is rebuilt, and any time a commit is made or merged to the `master` branch. But if you need to build the image on your own locally, do the following:

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. `cd` into this directory.
  3. Run `docker build --tag khulnasoft/docker-kali-ansible .`

## How to Use ##

  1. [Install Docker](https://docs.docker.com/engine/installation/).
  2. Pull this image from Docker Hub: `docker pull khulnasoft/docker-kali-ansible:latest` (or use the image you built earlier).
  3. Run a container from the image: `docker run --detach --privileged --cgroupns=host --volume=/sys/fs/cgroup:/sys/fs/cgroup:rw khulnasoft/docker-kali-ansible:latest`.
  4. Use Ansible inside the container:
    a. `docker exec --tty [container_id] env TERM=xterm ansible --version`
    b. `docker exec --tty [container_id] env TERM=xterm ansible-playbook /path/to/ansible/playbook.yml --syntax-check`

## Author Information ##

Shane Frasier - <jeremy.frasier@trio.dhs.gov>

Heavily based on
[geerlingguy/docker-debian11-ansible](https://github.com/geerlingguy/docker-debian11-ansible)
by [Jeff Geerling](https://www.jeffgeerling.com/) AKA
[@geerlingguy](https://github.com/geerlingguy).
