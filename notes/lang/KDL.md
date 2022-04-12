## Background

Configuration languages are pains to work with, is there a better language?

Some complains include:
* XML is too verbose. Opening and closing tag?

  In XML defense, it is a markup language, not a configuration language.

* INI doesn't have nesting

* TOML nesting is 'difficult'

* JSON is too "quoty"

* YAML has significant spacing and lacks tag/attributes concept


## What is KDL?

KDL is like XML but easier to read. 

In XML, the document mainly consists of:
* Tags
* Attributes
* Children

```xml
<tag attributeName="attributeValue">
  <children>This is <b>bold</b> text.</children>
</tag>
```

```kdl
tag attributeName=attributeValue {
    children {
        - "This is "
        b "bold"
        - "text."
    }
}
```

Official repo can be found [here](https://github.com/kdl-org/kdl).

## Why am I interested in KDL?

* It is simpler than XML.
* It handles nesting better than INI or TOML.
* It doesn't require quoting like JSON.
* It doesn't have significant indentantion like YAML.
* It has "block comment" `/-` :heart_eyes:

## Why am I not interested in KDL?

* Adoption is still early.