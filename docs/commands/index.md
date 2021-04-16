# Commands

There are a number of commands, that you can use to build and update your
blueprint as well as interact with the development environment.

You can always get a list of available commands by calling `docker-blueprint`
with `--help` flag.

Besides CLI commands, `docker-blueprint`
provides an easy way to interact with the running containers, circumventing
the lengthy docker-compose command:

```
docker-blueprint [service] [exec] <command>
```

## Running commands inside containers

For example, if you want to execute an `ls -l` command inside the
**default service** container, you could omit both `[service]` and `[exec]`
parts:

```
docker-blueprint ls -l
```

Which is a short form of this (short form is available only for the default service):

```
docker-blueprint app exec ls -l
```

You can replace `exec` verb with `sudo` to execute the command as the root
user inside container:

```
docker-blueprint sudo whoami # Output: root
```
