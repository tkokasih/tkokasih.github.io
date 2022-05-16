## Background

I need to work with some certificate and key and openssl is a kind of swiss army knife for this stuff.

## Overview

* `openssl` command is structured as
  ```
  openssl <command> <command options> <command arguments>
  ```
  Where command has 3 types:
  * Standard commands (`asn1parse`, `genrsa`, `pkcs12`, `req`, `rsa`, `ec`, `ecparam`, ...)
  * Message Digest commands (aka `dgst`, e.g. `md5`, `sha1`, `sha256`, ...)
  * Cipher commands (aka `enc`, e.g. `aes-256-ecb`, `base64`, `seed` ...)

* generally, the following options are accepted
  ```
  -in     : input file, usually private key
  -out    : output file
  -pubout : output the public key
  ```

## Cheatsheet

```
# Create ec public key from private key
openssl ec -in <private.key> -pubout

# Look into the asn1 structure
openssl asn1parse -in <key/cert>
```