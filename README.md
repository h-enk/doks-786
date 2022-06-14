# How to add a YouTube video to Doks

## Three steps

1. Embed a YouTube video using the built-in [Hugo shortcode](https://gohugo.io/content-management/shortcodes/#youtube), for example:

```md
{{< youtube BXNIhwwiYa0 >}}
```

2. Add `frame-src https://www.youtube.com;` to the `Content-Security-Policy` section in `./layouts/index.headers`, like so:

```bash
/*
  Strict-Transport-Security: max-age=31536000; includeSubDomains; preload
  X-Content-Type-Options: nosniff
  X-XSS-Protection: 1; mode=block
  Content-Security-Policy: default-src 'self'; frame-src https://www.youtube.com; frame-ancestors https://jamstackthemes.dev; manifest-src 'self' https://*.netlify.app; connect-src 'self' https://*.netlify.app; font-src 'self' https://*.netlify.app; img-src 'self' https://*.netlify.app data:; script-src 'self' https://*.netlify.app 'sha512-RBYr6Ld4w1yVqaACrgrBLQfPgGhj/1jyacA74WxJ1KM6KVcSWymwrdDwb3HDcdpwiNJ5yssot1He0U9vXoQVlg==' 'sha256-aWZ3y/RxbBYKHXH0z8+8ljrHG1mSBvyzSfxSMjBSaXk=' 'sha256-vOgyKS2vkH4n5TxBJpeh9SgzrE6LVGsAeOAvEST6oCc='; style-src 'self' https://*.netlify.app 'unsafe-inline'
  X-Frame-Options: SAMEORIGIN
  Referrer-Policy: strict-origin
  Feature-Policy: geolocation 'self'
  Cache-Control: public, max-age=31536000
  Access-Control-Allow-Origin: *
```

3. That's it!

## Example

- [beautiful-basbousa-70a70e.netlify.app](https://beautiful-basbousa-70a70e.netlify.app/)
