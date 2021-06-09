# Using Docker with the SAFE Template

This is an example of using docker with the SAFE Template.
This branch uses the `minimal` template and with regular `Dockerfile` that is not optimised for faster builds.

To build and run the server:

```bash
docker build -t safe-docker-example .
docker run --rm -it -p 8085:8085 safe-docker-example
```

To run the tests using docker-compose:

```bash
docker-compose -f docker-compose.server.test.yml up --build
```

# SAFE Template

This template can be used to generate a full-stack web application using the [SAFE Stack](https://safe-stack.github.io/). It was created using the dotnet [SAFE Template](https://safe-stack.github.io/docs/template-overview/). If you want to learn more about the template why not start with the [quick start](https://safe-stack.github.io/docs/quickstart/) guide?

## Install pre-requisites

You'll need to install the following pre-requisites in order to build SAFE applications

* The [.NET Core SDK](https://www.microsoft.com/net/download) 3.1 or higher.
* [npm](https://nodejs.org/en/download/) package manager.
* [Node LTS](https://nodejs.org/en/download/).

## Starting the application

Start the server:

```bash
cd src\Server\
dotnet watch run
```

Start the client:

```bash
npm install
dotnet tool restore
dotnet fable watch src/Client --run webpack-dev-server
```

Open a browser to `http://localhost:8080` to view the site.

## SAFE Stack Documentation

If you want to know more about the full Azure Stack and all of its components (including Azure) visit the official [SAFE documentation](https://safe-stack.github.io/docs/).

You will find more documentation about the used F# components at the following places:

* [Saturn](https://saturnframework.org/)
* [Fable](https://fable.io/docs/)
* [Elmish](https://elmish.github.io/elmish/)
