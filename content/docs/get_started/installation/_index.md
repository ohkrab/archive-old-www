---
---

# Installation

Krab binary can be downloaded from [GitHub](https://github.com/ohkrab/krab/releases). Other methods are listed below.

## asdf

Krab provides `asdf` [plugin](https://github.com/ohkrab/asdf-krab):

```sh
asdf plugin add krab https://github.com/ohkrab/asdf-krab.git
# or
asdf plugin add krab git@github.com:ohkrab/asdf-krab.git
```

Install desired version:

```sh
asdf install krab 0.2.4
```

Set it to your project:

```sh
asdf local krab 0.2.4
```

## docker 

To start a docker container `DATABASE_URL` environment variable must be provided.
By default "krab" reads configuration from `/etc/krab` that must be mounted as a volume,
the path can be changed by `KRAB_DIR` environment variable.

Pull the docker image:
```sh
docker pull qbart/krab:latest
```

Example:

```sh
docker run --rm                          \
        -e DATABASE_URL="..."            \
        -v ${HOME}/project1:/etc/krab:ro \
        qbart/krab:latest version
```



