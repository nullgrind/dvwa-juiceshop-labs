# DVWA Lab 01 — Authentication

## Objective
Analyze DVWA login authentication at the HTTP level and identify
how credentials are validated.

## Scope
- Application: DVWA
- Endpoint: /dvwa/login.php
- Security level: Low

## Request Analysis
The login functionality uses an HTTP POST request with
application/x-www-form-urlencoded parameters.

Observed parameters:
- username
- password
- Login

## Testing Performed
- Valid credentials
- Invalid password
- Empty password
- Non-existent username

## Observations
- Authentication success and failure responses are distinguishable.
- Error messages differ based on input.
- No rate limiting or account lockout observed.

## Root Cause
Authentication logic relies on direct credential comparison
without additional protections such as rate limiting or CAPTCHA.

## Impact
Allows attackers to enumerate valid credentials and attempt
brute-force attacks.

## Mitigation
- Implement rate limiting
- Generic error messages
- Account lockout or CAPTCHA
