# Background

Active Directory is ever-present in my company.
This is some basic that I gathered on this topic.

## What is Active Directory?

It is like a phone book for the organization.
This phonebook can be accessed using LDAP (Lightweight Directory Access Protocol) among other things.

## Any specific reason for "Company Phonebook"?

To know who's who.
Other system may have their own, but usually the login tied to Active Directory.

## How does this "company phonebook" looks like?

You can browse it with [AD Explorer](https://docs.microsoft.com/en-us/sysinternals/downloads/adexplorer).
Or plethora of other tools listed in here: https://ldap.com/ldap-tools/

## Any basic pointer to browse this "phonebook"?

* It is a tree
* Each "node" will have "attributes".
  Some common attributes:

  | attribute  | usual use  |
  |------------|------------|
  | dc         | domainComponent, like DNS domain name. example `dc=example, dc=com` |
  | uid        | userid |
  | cn         | commonName |
  | ou         | organizationalUnit |

  Example of LDAP path (aka DN = distinguished name, I like to think of it as fullpath)
  ```
  dc=com, dc=example, ou=singapore, ou=engineering, ou=people, uid=jdoe
  ```

  Each node along this path will have a bunch of other attributes.
  For example, in node `uid=jdoe`, it may have the following attributes:

  ```
  uid=jdoe
  cn=John Doe
  title=Chief Engineer
  lastLogin=2022.02.02 02:02:02
  ```

  ## What is typical usage of this

  A lot. One chief usage that I used is to control access, e.g. if I want Jenkins to be available to certain groups, I can use LDAP groups.

