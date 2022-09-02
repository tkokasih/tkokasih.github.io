## Background

I need to work with asn1 definition in a number of tasks as it is used in telco and cryptography.

## What is ASN1

ASN1 (Abstract Syntax Notation number 1) is a kind of data serialization format definition.
It has two parts: the definition and the encoding.

Below are examples of a definition, a message and how the message can be encoded by different encoding.

* First, an example of definition (adapted from Wikipedia):
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

* And below is an example of message that we will encode it in next examples:
    ```
    myQuestion FooQuestion ::= {
        trackingNumber  5,
        question        "Anybody there?"
    }
    ```

* This is example of the message encoded in XER
    ```
    <FooQuestion>
        <trackingNumber>5</trackingNumber>
        <question>Anybody there?</question>
    </FooQuestion>
    ```

* This is example of the message encoded in DER
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

I like to think of ASN.1 as a schema of schema, or meta-schema.
Examples of schema that we used to are XML Schema (XSD), JSONSchema or SQL DDL.
ASN.1 can be 'translated' or 'compiled' to those schema.
