[![Latest Stable Version](https://img.shields.io/packagist/v/seracid/php-mail-bounce-handler.svg?style=flat-square)](https://packagist.org/packages/seracpd/php-mail-bounce-handler)
[![Minimum PHP Version](https://img.shields.io/badge/php->%3D%205.4-8892BF.svg?style=flat-square)](https://php.net/)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/cd83d298ca004558ae6d3c8eeffede7b)](https://www.codacy.com/app/seracid/PhpMailBounceHandler?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=seracid/phpMailBounceHandler&amp;utm_campaign=Badge_Grade)
[![StyleCI](https://styleci.io/repos/100821082/shield?style=flat-square)](https://styleci.io/repos/100821082)
[![Gemnasium](https://img.shields.io/gemnasium/seracid/phpMailBounceHandler.svg?style=flat-square)](https://gemnasium.com/github.com/seracid/phpMailBounceHandler)

# PhpMailBounceHandler
The original project for this handler was: [CwsMailBounceHandler](https://github.com/crazy-max/CwsMailBounceHandler). 

📬 PHP class to help webmasters handle bounce-back, feedback loop and ARF mails in standard DSN (Delivery Status Notification, RFC-1894).
It checks your IMAP inbox or eml files and deletes or moves all bounced emails.
If a bounce is malformed, it tries to extract some useful information to parse status.

## Requirements

* PHP >= 5.4
* Enable the [php_imap](http://php.net/manual/en/book.imap.php) extension if you want to use the IMAP open mode.

## Installation with Composer

```bash
composer require seracid/php-mail-bounce-handler
```

And download the code:

```bash
composer install # or update
```

## Getting started

See `tests/test.php` file sample to help you.<br />
You can use the eml files in the `tests/emls` folder for testing.

## Post-process

A result object `SGT\MailBounceHandler\Models\Result` is available to process custom post-actions.

# Methods
## ImapHandler
**openLocal** - Open a IMAP mail box in local file system.<br />
**openRemote** - Open a remote IMAP mail box.<br />
**processMails** - Process the messages in a mailbox or a folder.<br />
**processMailMove** - Request mail message to be moved. <br />
**processMailDelete** - Request mail message be deleted. <br />
**isImapMailboxExists** - Confirms a mailbox exists (and optionally create it). <br />
**closeMailbox** - Closes IMAP connection in use and logs it.

## EmlFileHandler
**openEmlFolder** - Open a folder containing eml files on your system.<br />
**processMails** - Process the messages in a mailbox or a folder.<br />
**processMailMove** - Request mail message to be moved. <br />
**processMailDelete** - Request mail message be deleted. <br />

## Handler

**getStatusCodeExplanations** -Get explanations from DSN status code via the RFC 1893.<br />
**isMailboxOpenMode** - Check if open mode is mailbox.<br />
**isFileOpenMode** - Check if open mode is file.<br />
**isNeutralProcessMode** - Check if process mode is neutral mode.<br />
**isMoveProcessMode** - Check if process mode is move mode.<br />
**isDeleteProcessMode** - Check if process mode is delete mode.<br />
**getProcessMode** - The method to process bounces.<br />
**setNeutralProcessMode** - Set the method to process bounces to neutral. (default)<br />
**setMoveProcessMode** - Set the method to process bounces to move.<br />
**setDeleteProcessMode** - Set the method to process bounces to delete.<br />
**setProcessMode** - Set the method to process bounces.<br />
**getMailboxService** - Mailbox service.<br />
**setImapMailboxService** - Set the mailbox service to IMAP. (default)<br />
**setMailboxService** - Set the mailbox service.<br />
**getMailboxHost** - Mailbox host server.<br />
**setMailboxHost** - Set the mailbox host server. (default localhost)<br />
**getMailboxUsername** - The username of mailbox.<br />
**setMailboxUsername** - Set the username of mailbox.<br />
**setMailboxPassword** - Set the password needed to access mailbox.<br />
**getMailboxPort** - The mailbox server port number.<br />
**setMailboxPortPop3** - Set the mailbox server port number to POP3 (110).<br />
**setMailboxPortPop3TlsSsl** - Set the mailbox server port number to POP3 TLS/SSL (995).<br />
**setMailboxPortImap** - Set the mailbox server port number to IMAP (143). (default)<br />
**setMailboxPortImapTlsSsl** - Set the mailbox server port number to IMAP TLS/SSL (995).<br />
**setMailboxPort** - Set the mailbox server port number.<br />
**getMailboxSecurity** - The mailbox security option.<br />
**setMailboxSecurity** - Set the mailbox security option. (default const MAILBOX_SECURITY_NOTLS)<br />
**getMailboxCert** - Certificate validation.<br />
**setMailboxCertValidate** - Set the certificate validation to VALIDATE.<br />
**setMailboxCertNoValidate** - Set the certificate validation to NOVALIDATE. (default)<br />
**setMailboxCert** - Set the certificate validation.<br />
**getMailboxName** - Mailbox name.<br />
**setMailboxName** - Set the mailbox name, other choices are (Tasks, Spam, Replies, etc...). (default INBOX)<br />
**getMailboxHandler** - The resource handler for the opened mailbox (POP3/IMAP/NNTP/etc...).<br />
**getMaxMessages** - Maximum limit messages processed in one batch.<br />
**setMaxMessages** - Set the maximum limit messages processed in one batch (0 for unlimited).<br />
**isPurge** - Check if purge unknown messages.<br />
**setPurge** - Set the mailbox server port number.<br />
**getError** - The last error message.<br />

## License

LGPL. See `LICENSE` for more details.
