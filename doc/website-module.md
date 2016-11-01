# The Website Module

## Introduction

The **website** module manages per-site Nginx configuration

## Configuration directives

#### catalog
    catalog: website

Required

#### id
    id: example.net

Required

#### domain
    domain: example.net

Required

#### name
    name: [ example.net, www.example.net ]

A list of exact names, wildcard names or regular expressions prefixed with `~`.
Specifies which requests are served using this configuration. Corresponds to
nginx `server_name` directive.
Optional.

Default: `[ $id ]`

#### root
    root: /src/www/example.net

Specifies the root directory. Corresponds to nginx `root` directive
and apaches `DocumentRoot` directive.
Optional.

Default: `/var/www/$id`

#### tls
    tls: manual | letsencrypt | none

Specifies whether to enable SSL/TLS. 

Default: `letsencrypt`

#### tls_key
#### tls_certificate
#### tls_ca_certificate

Specifies path to needed file when `tls` is `manual`

#### enable_php
    enable_php: true | false

Enables PHP support

default: `false`

#### headers

Specifies additional HTTP headers to append.

Default: empty

#### locations

List of per-location directives.

