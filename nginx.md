### Nginx configuration for proxy pass to local node instance

With default ubuntu configuration put this file to `/etc/nginx/sites-enabled/<your_app>`

```nginx
server {
    listen 80;

    server_name you_domain.com www.your_domain.com;

    location / {
        proxy_pass http://localhost:3009;
    }
}
```
