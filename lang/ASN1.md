## Background

I need to work with asn1 definition in a number of tasks as it is used in telco and cryptography.

## What is ASN1

ASN1 (Abstract Syntax Notation number 1) is a kind of data serialization format definition.
It has two parts: the definition and the encoding.

* Example of definition (adapted from Wikipedia):
    ```
    FooProtocol DEFINITIONS ::= BEGIN
    FooQuestion ::= SEQUENCE {
        trackingNumber INTEGER(0..199),
        question       IA5String
    }

    FooAnswer :: SEQUENCE {
        questionNumber  INTEGER(10..20),
        answer          BOOLEAN
    }
    END
    ```

* Example of message (not yet serialized/encoded):
    ```
    myQuestion FooQuestion ::= {
        trackingNumber  5,
        question        "Anybody there?"
    }
    ```

* Encoded in XER
    ```
    <FooQuestion>
        <trackingNumber>5</trackingNumber>
        <question>Anybody there?</question>
    </FooQuestion>
    ```

* Encoded in DER
    ```
    30 13 02 01 05 16 0e 41 6e 79 62 6f 64 79 20 74 68 65 72 65 3f
    ```

  Which parses to
    ```
    30 - SEQUENCE
    13 - length
       02 - INTEGER
       01 - length
          05 - value (5)
       16 - IA5String
       0e - length
          41 6e 79 62 6f 64 79 20 74 68 65 72 65 3f - value ("Anybody there?")
    ```

## OK, Why?

I think of ASN.1 as a somewhat superset of schema, like XML Schema (XSD), JSONSchema, or even SQL DDL.
And yes, ASN.1 have a SQL encoding.

## Still confused?

Yeah, this is a low level stuff, but this is used often in cryptography and telco world.