# SAML2 METAGEN TEST ENVIRONMENT IDENTITY SERVER

[![](https://img.shields.io/github/issues/gridworkz/metagen-testenv.svg)](https://github.com/gridworkz/metagen-testenv-identityserver/issues "Issue tracker")

METAGEN Test Environment is aimed at Service Providers who want to test their integration with METAGEN without having real METAGEN identities available.
It consists of a WSO2 Identity Provider to run locally or on the providers' own server, where they can freely configure test identities.

The environment consists of two elements:
* the actual identity server, based on [WSO2-IS](https://github.com/wso2/product-is), [(repository github)](https://github.com/gridworkz/metagen-testenv-identityserver);
* a web backoffice based on Node.js which offers a simplified interface for the configuration of the Service Provider on the IS and the creation of identities [(github repository)] (https://github.com/gridworkz/metagen-testenv-backoffice).

## Docker

For installation with Docker refer to the [metagen-testenvironment] repository (https://github.com/gridworkz/metagen-testenv-docker)

## Installation without Docker

### Prerequisites

* Java 7 or 8

### Configuration

We recommend jdk1.8.0_162 (download and extract to /usr/lib/jvm)
```
sudo update-alternatives --install "/usr/bin/java" "java" "/usr/lib/jvm/jdk1.8.0_162/bin/java" 0
sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/lib/jvm/jdk1.8.0_162/bin/javac" 0
sudo update-alternatives --set java /usr/lib/jvm/jdk1.8.0_162/bin/java
sudo update-alternatives --set javac /usr/lib/jvm/jdk1.8.0_162/bin/javac
```

### Start

Start WSO2-IS with the following command (from the root of the test environment):

```
$ sh identity-server/bin/wso2server.sh start &
```
for windows environments use the .bat

## Service availability

It can take a few minutes to start up.
The identity server administration interface will be available in https: // localhost: 9443 / (user: admin, password: admin) 
but **it is not necessary** to open it as configuration tasks will be available on https://localhost:8080 (the backoffice) [(repository github)](https://github.com/gridworkz/metagen-testenvironment-backoffice)
