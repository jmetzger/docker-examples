# Project Template: Create a Docker image for a Java application

A template project to create a Docker image for a Java application.
The example application exposes an HTTP endpoint.

Features:

- The Docker build uses a
  [multi-stage build setup](https://docs.docker.com/build/building/multi-stage/)
  to minimize the size of the generated Docker image, which is 176MB
- Supports [Docker BuildKit](https://docs.docker.com/build/)
- Java 17 (Eclipse Temurin)
  [Maven](https://github.com/miguno/java-docker-build-tutorial/actions/workflows/maven.yml)
  and
  [Docker](https://github.com/miguno/java-docker-build-tutorial/actions/workflows/docker-image.yml)
- Optionally, uses

# Requirements

Docker must be installed on your local machine. That's it. You do not need a
Java JDK or Maven installed.

# Usage and Demo

**Step 1:** Build images 


```shell
# ***Creating an image may take a few minutes!***
$ docker build -t java-maven-app .
```


**Step 2:** Start a container for the Docker image.

```shell
$ docker run -d --name=myapp -p 8123:8123 java-maven-app
```

**Step 3:** Open another terminal and access the example API endpoint of the
running container.

```shell
$ curl http://localhost:8123/status
{"status": "idle"}
```

