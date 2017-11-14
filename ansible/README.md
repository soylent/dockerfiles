# Ansible

## Run

```sh
$ docker run --rm konstantin/ansible:2.4.1.0-alpine3.6 ansible --version
```

## Build

```sh
docker build . \
  --tag konstantin/ansible:2.4.1.0-alpine3.6 \
  --build-arg ansible_version=2.4.1.0 \
  --build-arg alpine_version=3.6 \
  --build-arg build_date=$(date +%Y-%m-%d)
```
