# Telegram Spring Boot Starter

[![Build Status](https://travis-ci.org/xabgesagtx/telegram-spring-boot-starter.svg?branch=master)](https://travis-ci.org/xabgesagtx/telegram-spring-boot-starter) [![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.github.xabgesagtx/telegram-spring-boot-starter/badge.svg)](https://mvnrepository.com/artifact/com.github.xabgesagtx/telegram-spring-boot-starter) [![Jitpack](https://jitpack.io/v/xabgesagtx/telegram-spring-boot-starter.svg)](https://jitpack.io/#xabgesagtx/telegram-spring-boot-starter)

This is a starter pom for a spring boot application with the [TelegramBots Java API](https://github.com/rubenlagus/TelegramBots).


The starter is available at maven central. Just add the following dependency to your pom:

```xml
<dependency>
	<groupId>com.github.xabgesagtx</groupId>
	<artifactId>telegram-spring-boot-starter</artifactId>
	<version>0.17</version>
</dependency>
```

For gradle users just add this to your dependencies:
```groovy
compile('com.github.xabgesagtx:telegram-spring-boot-starter:0.17')
```

The only thing you need to do after adding the depedency is to create a bean for a bot. E.g.:

```java
@Component
public class Bot extends TelegramLongPollingBot {
...
} 
```

The bot will then be registered for you automatically on startup.

## Configuration (version: 0.15+)
 
The following properties can be configured:

| property | description |
| -------- | ----------- |
| telegram.external-url | external base url for the webhook |
| telegram.internal-url | internal base url for the webhook |
| telegram.key-store | keystore for the server |
| telegram.key-store-password | keystore password for the server |
| telegram.path-to-certificate | full path for .pem public certificate keys |

You need to configure at least `external-url` and `internal-url` for webhook support. This configuration leaves the HTTPS handling to a proxy.

If you configure `key-store` for your HTTPS webhook bot, you need to configure `key-store-password` as well.

Also, `path-to-certificate` will only be used, if you configure the keystore.

In a regular spring boot setting these properties can be set in your `application.properties` or `application.yml`.

For more information on how these configuration options work, please refer to the [TelegramBots Java API](https://github.com/rubenlagus/TelegramBots).

## Example

An [implementation example](https://github.com/xabgesagtx/telegram-spring-boot-starter-example) is available too.
