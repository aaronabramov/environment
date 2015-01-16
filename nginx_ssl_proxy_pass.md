```nginx
    server {
        listen 443;
        server_name my.host.com;

        ssl_certificate /etc/nginx/cert.pem;
        ssl_certificate_key /etc/nginx/key.pem;

        ssl on;
        ssl_session_cache  builtin:1000  shared:SSL:10m;
        ssl_protocols  SSLv3;
        ssl_ciphers HIGH:!aNULL:!eNULL:!EXPORT:!CAMELLIA:!DES:!MD5:!PSK:!RC4;
        ssl_prefer_server_ciphers on;

        access_log /var/log/443.access.log;
        error_log /var/log/443.error.log;

        location / {
            proxy_pass https://localhost:3000;
        }
    }
```
