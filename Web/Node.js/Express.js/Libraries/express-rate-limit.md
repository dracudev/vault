## Overview
**express-rate-limit** is a middleware for **Express.js** that helps control the rate of incoming requests to prevent **brute-force attacks**, **abuse**, and **DDoS attacks** by limiting repeated requests from the same IP address.

---

## Installation
```bash
npm install express-rate-limit
```

---

## Basic Usage Example
```javascript
const express = require('express');
const rateLimit = require('express-rate-limit');

const app = express();

// Create a rate limiter
const limiter = rateLimit({
  windowMs: 15 * 60 * 1000, // 15 minutes
  max: 100, // limit each IP to 100 requests per windowMs
  message: 'Too many requests from this IP, please try again after 15 minutes.'
});

// Apply to all requests
app.use(limiter);

app.get('/', (req, res) => {
  res.send('Hello, world!');
});

app.listen(3000, () => console.log('Server running on port 3000'));
```

---

## Customizing Rate Limits per Route
```javascript
const loginLimiter = rateLimit({
  windowMs: 5 * 60 * 1000, // 5 minutes
  max: 5, // limit to 5 requests per windowMs
  message: 'Too many login attempts, please try again later.'
});

app.post('/login', loginLimiter, (req, res) => {
  res.send('Login route');
});
```

---

## Common Configuration Options
| Option         | Description                             |
|----------------|-----------------------------------------|
| `windowMs`     | Time frame for which requests are checked/remembered. |
| `max`          | Maximum number of connections during `windowMs`. |
| `message`      | Message sent when max is exceeded.      |
| `statusCode`   | Status code returned when limit is reached (default: 429). |
| `standardHeaders` | Use `RateLimit-*` headers (boolean). |
| `legacyHeaders`   | Enable/disable `X-RateLimit-*` headers. |

---

## Storing Rate Limit Data
By default, rate limits are stored in memory, which is not ideal for production. For better scalability, you can use **external stores** like **Redis**.

Example using `rate-limit-redis`:
```bash
npm install rate-limit-redis ioredis
```

```javascript
const RedisStore = require('rate-limit-redis');
const Redis = require('ioredis');

const redisClient = new Redis();

const limiter = rateLimit({
  store: new RedisStore({
    sendCommand: (...args) => redisClient.call(...args),
  }),
  windowMs: 15 * 60 * 1000,
  max: 100
});

app.use(limiter);
```

---

## Best Practices
- Customize limiters for sensitive routes like `/login`.
- Use external stores (Redis) for distributed deployments.
- Combine with other security middlewares like **helmet**.

---

## Useful Resources
- [express-rate-limit GitHub](https://github.com/nfriedly/express-rate-limit)
- [rate-limit-redis GitHub](https://github.com/wyattjoh/rate-limit-redis)

---

## Summary
`express-rate-limit` is a simple yet effective tool to mitigate abuse in your Express apps by restricting the number of requests within a time frame, enhancing the security and stability of your application.
