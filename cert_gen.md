```sh
openssl genrsa -out privatekey.pem 2048
openssl req -new -key privatekey.pem -out certrequest.csr
# common name should match the domain. e.g. `my-site.com` for `https://my-site.com:555`
openssl x509 -req -days 9999 -in certrequest.csr -signkey privatekey.pem -out certificate.pem
```
