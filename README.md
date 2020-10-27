# express middleware for server req/res record
## add below code in your express project to record server req/res
```
app.use(function (req, res, next) {
  const dateNow = new Date(Date.now()).toLocaleString('en-US', { hour12: false })
  console.log(dateNow, '|', req.method, 'from', req.originalUrl)
  next();
});
```

## server log will show as below example
```
10/27/2020, 14:23:04 | GET from /
```