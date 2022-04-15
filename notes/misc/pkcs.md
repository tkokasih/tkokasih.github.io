## Background

When working with keys and certificate, I still stumbled on PKCS#1, PKCS#8 and PEM.
A short reading will refresh my understanding.

## What are those?

* PKCS#1 [rfc8017](https://www.rfc-editor.org/rfc/rfc8017) - describe RSA

  One of which is how to represent private key, see Section A.1.2
  ```
  RSAPrivateKey ::= SEQUENCE {
    version           Version,
    modulus           INTEGER,  -- n
    publicExponent    INTEGER,  -- e
    privateExponent   INTEGER,  -- d
    prime1            INTEGER,  -- p
    prime2            INTEGER,  -- q
    exponent1         INTEGER,  -- d mod (p-1)
    exponent2         INTEGER,  -- d mod (q-1)
    coefficient       INTEGER,  -- (inverse of q) mod p
    otherPrimeInfos   OtherPrimeInfos OPTIONAL
  }
  ```
* PCKS#7 [rfc2315](https://www.rfc-editor.org/rfc/rfc2315) - Crytographic message

  I didn't have much mileage with this as I mostly deal with the keys and cert.

* PKCS#8 [rfc5208](https://www.rfc-editor.org/rfc/rfc5208) - Short rfc on generic wrapper for private key

  ```
  PrivateKeyInfo ::= SEQUENCE {
      version               Version,
      privateKeyAlgorithm   PrivateKeyAlgorithmIdentifier,
      privateKey            PrivateKey,
      atributes             [0] IMPLICIT Attributes OPTIONAL
  }

  Version ::= INTEGER

  PrivateKeyAlgorithmIdentifier ::= AlgorithmIdentifier

  PrivateKey ::= OCTET STRING

  Attributes ::= SET OF Attribute
  ```

* PKCS#10 [rfc2986](https://www.rfc-editor.org/rfc/rfc2986) - Certificate Request


* SEC1 [SEC1](http://www.secg.org/sec1-v2.pdf) - Describes EC key.

  For representation of private key, see Section C.4
  ```
  ECPrivateKey ::= SEQUENCE {
      version      INTEGER {ecPrivKeyVer1(1)} (ecPrivkeyVer1),
      privateKey   OCTET STRING,
      parameters   [0] ECDomainParameters {{ SECCurveNames }} OPTIONAL,
      publicKey    [1] BIT STRING OPTIONAL
  }
  ```
* PEM [rfc7468](https://www.rfc-editor.org/rfc/rfc7468) - A "finally-here" RFC

  Original PEM (Privacy-enhanced Electronic Mail) is [rfc1421](https://www.rfc-editor.org/rfc/rfc1421)..[rfc1424](https://www.rfc-editor.org/rfc/rfc1424).
  And it doesn't describe any representation of public/private keys.

  This rfc7468 documents what headers/footers commonly used to wrap the other representation.

  For openssl implementation, the wrapper can be found in [crypto/pem/pem.h](https://github.com/openssl/openssl/blob/master/include/openssl/pem.h)


  Examples:
  ```
  -----BEGIN PRIVATE KEY-----
  ..
  .. PKCS#8 Base64 Here ...
  ..
  -----END PRIVATE KEY-----


  -----BEGIN EC PRIVATE KEY-----
  ..
  .. SEC1 Private Key Base64 Here ...
  ..
  -----END PRIVATE KEY-----
  ```

## Cheatsheet

```
# ec to pkcs8
openssl pkcs8 -in <ec.key> -topk8 -nocrypt -out <pk8.key>

# pkcs8 to ec
openssl ec -in <pk8.key> -out <ec.key>

# check asn.1
openssl asn1parse -i -in <file>
```

## References
* [Stackoverflow on PEM](https://stackoverflow.com/a/5356351/851118)
* [Stackoverflow on EC and PKCS#1](https://security.stackexchange.com/a/84331/153170)
