# Deephaven custom server with Gradle

This project is a developer-targeted example for integrating code and 3rd-party libraries into a custom Deephaven server
using [Gradle](https://github.com/gradle/gradle). For a higher-level introduction to Deephaven, see the
[Deephaven Community Docs](https://deephaven.io/core/docs/).

For developers who prefer Maven, see [Deephaven custom server with Maven](https://github.com/deephaven-examples/deephaven-custom-server-maven).

For example purposes, this project depends on the [commons-math3](https://commons.apache.org/proper/commons-math/)
library, as well as some custom code to find the roots of the
[quadratic equation](https://en.wikipedia.org/wiki/Quadratic_equation).

### Getting started

To get up and running immediately with the server, you can run:

```shell
./gradlew run
```

By default, this will run the Deephaven gRPC API at `localhost:8080`.
Note: the current Netty-based distribution does not start a web server.

### Build distribution

To build the distribution, you can run:

```shell
./gradlew build
```

This will produce `build/distributions/foo-server.[tar|zip]`, which packages up all of the necessary jars into
`foo-server/lib/` and start scripts into `foo-server/bin/`.

### Build requirements

[Gradle requires](https://docs.gradle.org/7.4/userguide/compatibility.html) Java 8+ to run. The Deephaven server
requires Java 11+. If no suitable JDK is found, Gradle will
[auto-provision](https://docs.gradle.org/7.4/userguide/toolchains.html#sec:provisioning) a Java 11 JDK.

### Repositories

There are currently some external dependencies that aren't deployed to Maven Central.
To ensure these dependencies can be downloaded, see the
[repository settings](buildSrc/src/main/groovy/io.deephaven.java-repository-conventions.gradle).
