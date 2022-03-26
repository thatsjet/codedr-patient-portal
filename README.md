# CODE DOCTOR: Patient Portal

Intentionally vulnerable patient portal application for demonstration of vulnerabilities and remediation

## Functional requirements

- Schedule appointments
- Patient/provider messaging
- Chart
- Prescription refills
- Roles: Hospital administrator, Doctors, Nurses, patients (default)

## Remediation By vuln type (OWTT)

### A01 Broken Access Control

    - Viewing other patients data (IDOR)
    - API direct access (CORS) without input validation (prescription ordering)
    - JWT manipulation
    - Elevation of privilege
    - Forced browsing admin page

### A02 Cryptographic Failures

    - Weak hash algorithm for password storage

### A03 Injection

    - XSS in messaging app / search

### A04 Insecure Design

    - Both admin/user interface in the same application

### A05 Security Misconfiguration

    - Content security policy
    - Mongo DB without access control
    - HTTP index on directory allows for file enumeration

### A06 Vulnerable and Outdated Components

    - nuff said

### A07 Identification and Authentication Failures

    - Weak passwords allowed
    - Timing based enumeration
    - Forgot password weak challenge (last 4, dogs name, mother maiden, etc.)
    - session in URL
    - session reuse on login success
    - no session invalidation (cookie delete only)

### A08 Software and Data Integrity Failures

    - File upload without validation allows for IDOR

### A09 Security Logging and Monitoring Failures

    - Non-existent

### A10 Server Side Request Forgery (SSRF)

    - Patient lookup by location (each location different API, select)