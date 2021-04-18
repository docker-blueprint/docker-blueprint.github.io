# Getting Started

## Requirements

Any platform that is able to run **docker**, has **git** and **bash 4+**
installed.

Although not a requirement, a [standalone version of yq](https://github.com/mikefarah/yq#install)
is recommended in order to get the most performant experience (otherwise we
will try our best & use docker version of yq, which is slower).

## How  to install

Installation is done by cloning this repository and symlinking the
`entrypoint.sh` script to one of the `bin` directories on the system
(`/usr/local/bin` by default).

To ease the process of installation you can invoke this one-liner that will
handle the installation process for you:

with **curl**:

```sh
bash -c "$(curl -fsSL https://raw.githubusercontent.com/docker-blueprint/core/master/install.sh)"
```

with **wget**:

```sh
bash -c "$(wget -O- https://raw.githubusercontent.com/docker-blueprint/core/master/install.sh)"
```

Of course, you can inspect install script yourself prior to download:
https://github.com/docker-blueprint/core/blob/master/install.sh
