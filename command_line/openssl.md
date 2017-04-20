## OpenSSL

### Display information about certificate

```
echo | openssl s_client -showcerts -servername example.com -connect example.com:443 2>/dev/null | openssl x509 -inform pem -noout -text
```

Source: [https://serverfault.com/a/661982](https://serverfault.com/a/661982)
