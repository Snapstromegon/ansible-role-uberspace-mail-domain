# Ansible Role: uberspace-mail-domain

This is part of the uberspace roles collection.

This is meant to be used on your [Uberspace](https://uberspace.de/).

Please be aware, that I'm neither part of the Uberspace team, nor am I associated to them other than having some Uberspaces myself.
This project was created, because I wanted to use the roles for myself and thought they were okay-ish enough to share them.

## What is this (from the uberspace manual)

In order to use your own domain for mail with your Uberspace, you need to first set it up using our uberspace tool.

You can find the documentation of the replaced tool `uberspace mail domain` in the Uberspace Manual [here](https://manual.uberspace.de/mail-domains.html).

## Usage

| Variable | Choices/Default                            | Description                                                          |
| :------: | :----------------------------------------- | :------------------------------------------------------------------- |
|  domain  |                                            | The domain you want to recieve mails on                              |
|  state   | <ul><li>present ✔</li><li>absent</li></ul> | "present" to be able to recieve mails, "absent" to remove the domain |
| domains  | []                                         | A list of domain, state combinations to set multiple domains at once |

## Examples

### Add Domain

```yaml
- hosts: uberspace
  roles:
    - name: uberspace-mail-domain
      domain: isabell.example
```

### Remove Domain

```yaml
- hosts: uberspace
  roles:
    - name: uberspace-mail-catchall
      domain: isabell.example
      state: absent
```

### Set multiple Domains

```yaml
- hosts: uberspace
  roles:
    - name: uberspace-mail-domain
      domains:
        - domain: present.isabell.example
        - domain: absent.isabell.example
          state: absent
```
