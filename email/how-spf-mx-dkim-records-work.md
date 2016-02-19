# How SPF, MX, and DKIM records work for email

## SPF records

When a mail server receives an email from `someone@fahrenheit.io`, it sends a request to
the DNS to ask for SPF records, essentially asking "which servers are authorized to send
emails on your behalf?" If the incoming email came from any other server, it is rejected.

## MX records

When a mail server sends an email to `someone@fahrenheit.io`, the server will forward the
email to the mail server specified in the MX record.

## DKIM records

Yahoo started this protocol as a method of private/public key authentication. DKIM records
contain public keys which can verify an email's signature. Outgoing mail servers with DKIM
will sign all outgoing mail with the private key, which can be verified with the public key.

Note that this is why Yahoo email addresses (or any email address with a mail server using
DKIM) cannot be forwarded/impersonated by mailing lists such as SimpleLists. If anyone tries
to send an email 'from' the DKIM address without the private key for signing, the email will
be rejected by the receiving mail server. This is why such mailing lists have to send email
'on behalf of' a Yahoo email address, instead of invisibly impersonating them.
