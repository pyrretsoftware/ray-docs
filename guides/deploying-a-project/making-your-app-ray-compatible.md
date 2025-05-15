---
icon: code
---

# Making your app ray-compatible

The only thing you need to change in your app for it to be compatible with ray is the port it uses. Ray will automatically expose the `ray-port` environment variable to your app, so you simply need to have your application use that port.

For example, in an express.js application:

```javascript
const express = require('express')
const app = express()
const port = process.env["ray-port"] //it's that simple

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)
})

```

{% hint style="success" %}
Tip: the ray-port environment variable is also available under the name "RAY\_PORT". &#x20;
{% endhint %}
