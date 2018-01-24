Nanobox MailHog implementation
------------------------------

Install MailHog into your workflow, making it available at the URL `/mailbox`.

Make sure to have the following environment variables set for Nanobox:

```bash
$ nanobox evar add dry-run MAIL_USER="<username>" MAIL_PASS="<password>"
$ nanobox evar add test MAIL_USER="<username>" MAIL_PASS="<password>"
$ nanobox evar add prod DISABLE_MAILHOG=1
```

In the development environment MailHog is accessible without authentication. In all other environments authentication 
is set by the username and password from the environment variables.

## Symfony configuration example

```yaml
swiftmailer:
  transport: smtp 
  host: localhost 
  port: 1025 
  spool: 
    type: memory
```