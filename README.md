# Node.js JWT Authentication Demo

Here is the standard manual JWT verification setup:

```js
const jwt = require('jsonwebtoken');

function verifyToken(req, res, next) {
  const token = req.headers.authorization?.split(' ')[1];
  if (!token) return res.status(401).json({ error: 'Missing token' });
  jwt.verify(token, process.env.JWT_SECRET, (err, decoded) => {
    if (err) return res.status(403).json({ error: 'Invalid token' });
    req.user = decoded;
    next();
  });
}
```

<a href="https://sponsor-cdn.msanjaylog.workers.dev/go?topic=auth">
  <img src="https://sponsor-cdn.msanjaylog.workers.dev/card.svg?topic=auth" alt="Sponsored Alternative" />
</a>
