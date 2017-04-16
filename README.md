CloudSecurity
============
This repository is all about cloud security using [Spring Boot](https://projects.spring.io/spring-boot), 
[Spring Cloud (Config)](http://projects.spring.io/spring-cloud) and [Vault](https://www.vaultproject.io).

# config-client
This simple web application exposes some REST services with the endpoints `/`, `/users` and `/credentials`. Based on the
active Spring profile the configuration files used are not encrypted (**default**), secured using jasypt (**jasypt**),
or secured using vault (**vault**).

## Profile default
Configuration files are not protected at all, even sensitive configuration properties are available in plain text.

## Profile jasypt
This profile is using [Jasypt for Spring Boot](https://github.com/ulisesbocchio/jasypt-spring-boot) to secure
sensitive configuration properties. You have to provide an environment variable named `jasypt.encryptor.password` with
the value `config-client-jasypt` to decrypt the database password during application start.

## Profile vault
This profile is using [Vault](https://www.vaultproject.io) to secure sensitive configuration properties.

# config-repo
This folder contains all configuration files for all profiles used with the **config-client** application.

# config-server
This project contains the Spring Cloud Config server which must be started before using any of the other web applications.
It's available on port 8888 and will use the configuration files provided in the **config-repo** folder.

## Meta
[![Build Status](https://travis-ci.org/dschadow/CloudSecurity.svg)](https://travis-ci.org/dschadow/CloudSecurity)
[![Code Climate](https://codeclimate.com/github/dschadow/CloudSecurity/badges/gpa.svg)](https://codeclimate.com/github/dschadow/CloudSecurity)
[![codecov](https://codecov.io/gh/dschadow/CloudSecurity/branch/develop/graph/badge.svg)](https://codecov.io/gh/dschadow/CloudSecurity)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
