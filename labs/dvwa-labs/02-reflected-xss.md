# DVWA Lab 02 — Reflected XSS
Burp Repeater is used to manipulate and observe HTTP traffic, but JavaScript execution and cookie access only occur in the browser runtime

## Objective
Identify and analyze reflected cross-site scripting in DVWA
and understand execution context and impact.

## Scope
- Application: DVWA
- Vulnerability: Reflected XSS
- Endpoint: /dvwa/vulnerabilities/xss_r/
- Security level: Low

## Injection Point
User-controlled input via the `name` GET parameter is reflected
directly into the HTML response without encoding.

## Context Analysis
Injected input is rendered in the HTML body context,
allowing arbitrary JavaScript execution.

## Proof of Execution
Injected JavaScript executes successfully in the victim’s browser,
demonstrated via controlled DOM manipulation.

## Impact
An attacker could:
- Execute arbitrary JavaScript in the user’s session
- Access non-HttpOnly cookies
- Perform authenticated actions on behalf of the user

## Root Cause
Lack of output encoding and input validation for reflected user input.

## Mitigation
- Encode output based on context
- Use Content Security Policy (CSP)
- Set session cookies as HttpOnly
