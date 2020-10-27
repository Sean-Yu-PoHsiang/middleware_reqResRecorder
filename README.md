# express middleware for server req/res record
## add below code in your express project to record server req/res
```
app.use(function (req, res, next) {
  const reqDate = new Date(Date.now())
  const reqDateFormat = reqDate.toLocaleString('en-US', { hour12: false })

  res.once('finish', () => {
    const resDate = new Date(Date.now())

    console.log(reqDateFormat, '|', req.method, 'from', req.originalUrl, '|', 'total time:', (resDate - reqDate) + 'ms')
  })

  next()
})
```

## server log will show as below example
```
10/27/2020, 15:56:42 | GET from /new | total time: 9ms
```