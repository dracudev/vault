## Overview
**Helmet** is a middleware for **Express.js** that helps secure applications by setting various HTTP headers. It mitigates common vulnerabilities such as **Cross-Site Scripting (XSS)**, **Clickjacking**, and others.

---

## Installation
```bash
npm install helmet
```

---

## Basic Usage
```javascript
const express = require('express');
const helmet = require('helmet');

const app = express();

// Apply Helmet to secure HTTP headers
app.use(helmet());

app.get('/', (req, res) => {
  res.send('Hello, secure world!');
});

app.listen(3000, () => console.log('Server running on port 3000'));
```

---

## Security Features Provided by Helmet
Helmet sets or disables the following headers for better security:

| Middleware              | Purpose |
|-------------------------|---------|
| `helmet.contentSecurityPolicy()` | Prevent XSS and data injection attacks by controlling sources of content. |
| `helmet.dnsPrefetchControl()`    | Controls browser DNS prefetching. |
| `helmet.expectCt()`              | Helps prevent misissued SSL certificates. |
| `helmet.frameguard()`            | Prevents clickjacking by controlling the `X-Frame-Options` header. |
| `helmet.hidePoweredBy()`         | Removes `X-Powered-By` header to obscure tech stack. |
| `helmet.hsts()`                  | Enforces HTTPS via the `Strict-Transport-Security` header. |
| `helmet.ieNoOpen()`              | Prevents IE from executing downloads in the site's context. |
| `helmet.noSniff()`               | Prevents MIME type sniffing. |
| `helmet.permittedCrossDomainPolicies()` | Controls Adobe Flash and Acrobat cross-domain policies. |
| `helmet.referrerPolicy()`        | Controls information sent in the `Referer` header. |
| `helmet.xssFilter()`             | Sets the `X-XSS-Protection` header to mitigate XSS attacks. |

---

## Example: Customizing Helmet
```javascript
app.use(
  helmet({
    contentSecurityPolicy: false, // Disable CSP for development
    frameguard: { action: 'deny' },
    referrerPolicy: { policy: 'no-referrer' }
  })
);
```

---

## Combining with Other Security Middlewares
- **express-rate-limit**: Rate limiting to prevent brute force attacks.
- **cors**: Configures Cross-Origin Resource Sharing.
- **csurf**: Provides CSRF protection.

Example:
```bash
npm install express-rate-limit cors csurf
```

```javascript
const rateLimit = require('express-rate-limit');
const cors = require('cors');
const csurf = require('csurf');

app.use(cors());
app.use(rateLimit({ windowMs: 15 * 60 * 1000, max: 100 }));
app.use(csurf());
```

---

## Best Practices
- Regularly update Helmet to incorporate latest protections.
- Review which security headers are most relevant for your application.
- Enable **Content Security Policy (CSP)** in production.

---

## Useful Resources
- [Helmet Official Documentation](https://helmetjs.github.io/)
- [OWASP Secure Headers Project](https://owasp.org/www-project-secure-headers/)

---

## Summary
Helmet is a crucial part of securing Express.js applications. By automatically setting secure HTTP headers, it helps protect against many common web vulnerabilities with minimal configuration.
