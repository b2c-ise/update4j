# [![update4j-logo][3]][3]

[![Build Status](https://travis-ci.org/update4j/update4j.svg?branch=master)](https://travis-ci.org/update4j/update4j)   [![Apache License](https://img.shields.io/badge/license-Apache%20License%202.0-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0)   ![Java-9+](https://img.shields.io/badge/java-9%2B-orange.svg)   [![Maven Release](https://img.shields.io/badge/maven%20central-v1.4.0-yellow.svg)](https://search.maven.org/search?q=org.update4j)    [![Gitter](https://badges.gitter.im/update4j/update4j.svg)](https://gitter.im/update4j/update4j?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)


**Read the [documentation](https://github.com/update4j/update4j/wiki/Documentation), explore the [JavaDoc](http://docs.update4j.org/javadoc/update4j/index.html), or [see it in action](https://github.com/update4j/update4j/wiki/Demo-Application)**

Auto-updater and launcher for your distributed applications. Built with Java 9's module system in mind.

## Screenshots

### Headless
<sup>Downloads 4 files then launches `hello-world.jar`. You can see that subsequent runs won't download again.</sup>
[![headless][2]][2]

### JavaFX

<sup>Downloads 4 files then launches `hello-world.jar`</sup>
[![javafx][1]][1]



## Overview

The update4j framework is the first auto-update and launcher framework completely compatible with Java 9 and up. Easily host your application files anywhere in the cloud accessible via a URL (even Google Drive, Dropbox, Amazon S3, or Maven Central)
and you can synchronize them with all your distributed applications.

In update4j _you_ have ultimate control of every process, from startup - update - launch - shutdown; unlike other auto-update frameworks that yields over the control only once the business application was launched. In addition, every single piece of code is completely updatable; [even the framework itself](https://github.com/update4j/update4j/wiki/Documentation#updating-update4j-itself), once a new version is released!

## Installation & Usage

You can [download](https://repo1.maven.org/maven2/org/update4j/update4j/1.4.0/update4j-1.4.0.jar) or install using Maven:

```xml
<dependency>
    <groupId>org.update4j</groupId>
    <artifactId>update4j</artifactId>
    <version>1.4.0</version>
</dependency>
```

You can use it as a regular dependency, or you may run it as a runnable JAR file. 

To run it in the modulepath, use either of:

```shell
$ java -p update4j-1.4.0.jar -m org.update4j
$ java -p . -m org.update4j

```

To run it in the classpath, use either of:

```shell
$ java -jar update4j-1.4.0.jar
$ java -cp * org.update4j.Bootstrap
```

For more information refer to [Starting the Application](https://github.com/update4j/update4j/wiki/Documentation#starting-the-application) in the wiki.


## What's New in 1.4.x &mdash; [Migration Guide](https://github.com/update4j/update4j/wiki/Migration-to-1.4.x)
  * Added dependency injection framework to communicate between the bootstrap and service provider.
  * Consequently, removed provider consumers at update and launch, and passing args at launch.
  * Removed many confusing `getXxxProperty()` methods in `Configuration` class.
  * You can now add properties to a config dynamically at runtime.
  * Locate explicit service providers even if not properly registered as required by `ServiceLoader`.
  * Made many service methods `default`.
  * Added `osFromFilename()` method in `FileMetadata` builder.
  * Changed how `--delegate` argument in `Bootstrap` works.


## Attribution

This project was highly influenced by [edvin/fxlauncher](https://github.com/edvin/fxlauncher/). Thanks for the insights
that made this possible.

## License

This project is licensed under the [Apache Software License 2.0](http://www.apache.org/licenses/LICENSE-2.0)


  [1]: https://i.stack.imgur.com/Hz1G7.gif
  [2]: https://i.stack.imgur.com/Ttf8Z.gif
  [3]: https://i.stack.imgur.com/L6WAF.jpg
