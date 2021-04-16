<div class="has-text-centered">
    <a class="pure-button"
       href="/#/getting-started/index">
       Skip to the 'Getting Started' Section
    </a>
</div>

Welcome to the documentation page `docker-blueprint` - a tool that
helps you build and share modular _ephemeral_ development environments based
[docker](https://docs.docker.com/get-started/) & [docker-compose](https://docs.docker.com/compose/).

?> Ephemeral [ ih-fem-er-uhl ] - lasting a very short time; short-lived
(dictionary.com)

Usually, it takes trial and error in order to build just the right `Dockerfile`
for your project. You have to get deep into the specifics of particular
technologies you are using in order to install the right dependencies and make
your application work in a container.

With `docker-blueprint` you can take advantage of a library of open and modular
blueprints that help you generate `Dockerfile` and `docker-compose.yml` files
for you.

Initializing a blueprint for your existing project is as simple running `new`
command:

<!-- tabs:start -->

#### ** PHP **

```
docker-blueprint new php
```

#### ** Laravel **

```
docker-blueprint new php --env laravel --with mysql redis
```

<!-- tabs:end -->

?> **PRO TIP:** You can use short version of `docker-blueprint` - `dob` in order
to save keystrokes.

Better yet, `docker-blueprint` makes working with a containerized development
environment a breeze - blurring the line between files on your work machine
and runtime environment inside the container!


<!-- tabs:start -->

#### ** PHP **

```
docker-blueprint php -i
```

#### ** Laravel **

```
docker-blueprint php artisan migrate
```

<!-- tabs:end -->

Once you have initialized the blueprint for your project - you will have a
`docker-blueprint.yml` file in its directory, which describes your project
configuration (such as runtime version, environment & modules you used).
Now you can push these changes into a VCS repository and reproduce this same
development environment on another machine:

```
docker-blueprint up
```

Interested in setting up your development environment?

Let's get to the next chapter for the instructions of how to install and use
blueprints.
