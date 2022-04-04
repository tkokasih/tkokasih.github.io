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