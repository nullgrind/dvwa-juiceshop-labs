# Lab 01 — Burp Proxy + Repeater Fundamentals (OWASP Juice Shop)

## Objective
Validate a reproducible interception workflow (browser → Burp → target), capture real HTTP traffic, replay it in Repeater, and document the difference between browser execution and Burp request replay.

## Environment
- Attacker: Kali Linux (Firefox + Burp Suite Community/Pro)
- Target: OWASP Juice Shop (Docker) on Ubuntu Server VM
- Target URL: http://<UBUNTU_VM_IP>:3000
- Burp Proxy Listener: 127.0.0.1:8080

## Steps to Reproduce

### 1) Start the target (Ubuntu VM)
Run Juice Shop via Docker:
- Command: `docker run --rm -p 3000:3000 --name juice-shop bkimminich/juice-shop`

Verify service:
- `curl -I http://127.0.0.1:3000`

### 2) Configure interception (Kali)
- Burp Proxy listener active on 127.0.0.1:8080
- Firefox configured to proxy HTTP/HTTPS via 127.0.0.1:8080

Browse to:
- http://<UBUNTU_VM_IP>:3000

**Expected:** Requests appear in Burp Proxy → HTTP history.

### 3) Replay a request in Repeater
- Select a request to the target in HTTP history
- Send to Repeater and click Send
- Observe status code and headers

### 4) Demonstrate browser vs Burp execution
- In the browser DevTools console, run: `document.title`
- Note: Burp can replay HTTP traffic but cannot execute JS or provide DOM output.

## Evidence
- Screenshot: Burp HTTP history entries to the target (evidence/01-http-history.png)
- Screenshot: Repeater baseline request + response (evidence/02-repeater-baseline.png)
- Screenshot: Repeater with added `X-Lab:` header (evidence/03-repeater-header-change.png)
- Screenshot: Browser DevTools `document.title` output (evidence/04-devtools-dom-proof.png)

## Key Takeaways
- Burp Proxy enables interception/modification of HTTP(S) traffic between browser and server.
- Burp Repeater is for manual request replay and controlled mutation.
- Burp does **not** render pages or execute JavaScript; XSS must be validated in a real browser context.
