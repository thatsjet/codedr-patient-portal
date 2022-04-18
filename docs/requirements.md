Code Doctor Patient Portal

Basic app requirements

Customers: CustID, Name, Email, Token, Password

Security Requirements
 - authn
 - TLS (self-signed cert)
 - One app, many solutions directories

Flaw types:
- IDOR / broken access control
	- show centralizing vs. each code block
- JWT decode vs. verify
- XSS/CSP
- NoSQLi
- path traversal
- poor crypto (outdated/weak)
- insecure config (express helmet)
- vulnerable components
- SSRF
- logging/monitoring (use ELVS)
	- Do a demo of this at a con

Back everything up to personal GitHub and Google Drive.