# Typical workflow in a project

A typical workflow using `docker-blueprint` consists calling the `new` command,
which will usually try its best to do everything in one go, producing a working
development environment when it finishes.

After you have your `docker-blueprint.yml` generated you can call `up` command
in order to bring up your environment on another machine. Since it resides in a
container it will not pollute global workspace. Therefore it is safe for other
developers to reproduce your development environment without any fear of
breaking their local runtime or database configuration.

If at any time you need to build fresh `Dockerfile` and `docker-compose` files
that would reflect the current configuration, you can do so with `build` command
using `--force` flag.

## Making a `new` blueprint

To automatically initialize `docker-blueprint` for your project, the `new`
command is used:

```
docker-blueprint new <blueprint> [--env <name>] [--with <modules>]
```

It automatically **pulls** the `<blueprint>` from a [GitHub](https://github.com)
repository, specified in the form of `[VENDOR/]NAME[:TAG]` and checks out
the branch specified as `TAG` (which defaults to `master`).

For example, calling the following command:

```
docker-blueprint new php --env laravel --with mysql redis
```

- Downloads the latest version of
[docker-blueprint/php](https://github.com/docker-blueprint/php)
blueprint from GitHub
- Generates `docker-blueprint.yml` file that specifies blueprint environment,
a list of modules and other project metadata
- Builds `docker-compose` and `Dockerfile` files depending on the environment
and specified modules
- Brings up the docker-compose project for the default [project context](),
building required docker images, if necessary

In this command, `--env` flag specifies the blueprint [environment]() - a
preset of the blueprint for a particular technology or framework (i.e. Laravel,
Wordpress, etc for PHP; Vue, React, etc for Web Front-End; and so on).

On the other hand, `--with` option specifies a list of [blueprint modules]()
to use in the project. For example, while some projects might use MySQL,
others could be using PostgreSQL.
Because blueprints are modular, it is possible to specify various combinations
of technologies for the same blueprint depending on project's requirements and
build `docker-compose` and `Dockerfile` files containing those particular
technologies.

## Bringing `up` the project

Once the blueprint has been generated for the first time, it will try to bring
the project up automatically. To do this yourself later on another machine
using generated files, you can simply invoke:

```
docker-blueprint [--context <name>] up
```

## `Building` the image

In order to build docker image for the given context without bringing containers
up, you can use the `build` command:

```
docker-blueprint [--context <name>] build [--force] [<tag>]
```

This can be especially useful in a CI/CD pipeline, where you can use
`production` project context in order to build an tag image with a single command:

```
docker-blueprint --context production build my_project:latest
```

Using the `--force` flag you can regenerate already existing `Dockerfile` and
`docker-compose` files in order to sync them with what's defined inside
`docker-blueprint.yml`.

!> **WARNING:** Passing `--force` flag makes this command destructive.
It is advised to have your project files backed up in VCS prior to using this
flag in case you will want to revert changes.
