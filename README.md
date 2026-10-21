# Reflected XSS via Unsanitized GET Parameter  
*(Responsible Disclosure Case Study)*

## Overview
During casual testing of a public-facing web application, I identified a **Reflected Cross-Site Scripting (XSS)** vulnerability caused by improper handling of a GET parameter.  
The issue was responsibly disclosed to the site administrators and subsequently fixed.

This repository documents the vulnerability **in a sanitized form**, without disclosing sensitive details or target identifiers.

---

## Vulnerability Details

- **Type:** Reflected XSS
- **Vector:** GET parameter reflected into HTML response
- **Root Cause:** Missing context-aware output encoding
- **Attack Surface:** User-controlled input rendered directly in HTML

---

## Proof of Concept (Sanitized)

Example payload demonstrating the issue:
**GET /?param=**

When injected, the payload was rendered into the HTML response without proper sanitization, resulting in JavaScript execution in the browser context.

> ⚠️ Note:  
> The actual domain, endpoint, and parameter names are intentionally omitted.

---

## Impact

Successful exploitation could allow:
- Execution of arbitrary JavaScript in the victim’s browser
- Phishing attacks
- Content manipulation
- User trust abuse within the affected domain

---

## Disclosure Process

- The vulnerability was reported directly to the site administrators via email.
- A clear description and proof of concept were provided.
- The issue was acknowledged and fixed by the maintainers.

No further testing was performed after confirmation.

---

## Ethical Considerations

- No data was accessed or modified.
- The vulnerability was not exploited beyond proof of concept.
- This case follows responsible disclosure principles.

---

## Key Takeaways

- Even simple reflected inputs can lead to critical client-side vulnerabilities.
- Proper output encoding must be applied based on rendering context.
- Clear and ethical communication with maintainers leads to fast remediation.

---

## Disclaimer

This repository is intended for educational and portfolio purposes only.  
All sensitive details have been removed to prevent misuse.
