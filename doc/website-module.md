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

Optional.
Default: [ $id ]

#### root

Optional.
Default: /var/www/$id

