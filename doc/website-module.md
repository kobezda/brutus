# The Website Module

## Introduction

The **website** module manages per-site Nginx configuration

## Configuration directives

#### catalog
> Syntax: `catalog: website`  


#### id
> Syntax: `id: `*`website_id`*  
> Example: `id: example.net`  


#### domain
> Syntax: `domain: `*`domain_name`*  
> Example: `domain: example.net`  
> References: [domain id][brutus_domain_id] 


#### name
> Syntax: `name: [ `*`server_name`*`, ... ]`  
> Default: `name: [ `**`$id`**` ]`  
> Example: `name: [ example.net, www.example.net ]`  


A list of exact names, wildcard names or regular expressions prefixed with `~`.
Specifies which requests are served using this configuration.
Corresponds to nginx [`server_name`][ngx_server_name] directive.

#### root
> Syntax: `root: `*`path`*  
> Default: `root: /var/www/`**`$id`**  
> Example: `root: /src/www/example.net`

Specifies the root directory.
Corresponds to nginx [`root`][ngx_root] directive
and apaches [`DocumentRoot`][ap_documentroot] directive.

#### tls
> Syntax: `tls: manual | letsencrypt | none`  
> Default: `tls: letsencrypt`

Specifies whether to enable SSL/TLS.

#### tls_key
#### tls_certificate
#### tls_ca_certificate,
> Syntax: `tls_key: `*`path`*  
> Example: `tls_key: /etc/nginx/ssl/example.net.key`

Specifies path to needed files when `tls` is `manual`
Corresponds to nginx 
[`ssl_certificate_key`][ngx_ssl_certificate_key]
[`ssl_certificate`][ngx_ssl_certificate]
[`ssl_trusted_certificate`][ngx_ssl_trusted_certificate]


#### enable_php
> Syntax: `enable_php: true | false`  
> Default: `enable_php: false`

Enables PHP support through PHP-FPM

#### headers

Specifies additional HTTP headers to append.
Corresponds to nginx [`add_header`][ngx_add_header] directive.

#### locations

List of per-location directives.


[ngx_server_name]: http://nginx.org/en/docs/http/ngx_http_core_module.html#server_name "Nginx: server_name"
[ngx_root]: http://nginx.org/en/docs/http/ngx_http_core_module.html#root "Nginx: root"
[ngx_ssl_certificate_key]: http://nginx.org/en/docs/http/ngx_http_ssl_module.html#ssl_certificate_key "Nginx: ssl_certificate_key"
[ngx_ssl_certificate]: http://nginx.org/en/docs/http/ngx_http_ssl_module.html#ssl_certificate "Nginx: ssl_certificate"
[ngx_ssl_trusted_certificate]: http://nginx.org/en/docs/http/ngx_http_ssl_module.html#ssl_trusted_certificate "Nginx: ssl_trusted_certificate"
[ngx_add_header]: http://nginx.org/en/docs/http/ngx_http_headers_module.html#add_header "Nginx: add_header"
[ap_documentroot]: https://httpd.apache.org/docs/current/mod/core.html#documentroot "Apache: DocumentRoot"
[brutus_domain_id]: domain-module.md#id "Brutus: domain id"
