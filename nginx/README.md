
1. docker-compose up -d
2. docker-compose exec nginx apk add bash
3. docker-compose exec nginx bash
**↣ apk add vim.**

vim /etc/nginx/conf.d/default.conf

```
upstream nodes {
  server node1;
  server node2;
}

server {
    listen       80;
    server_name  localhost;

    location / {
      proxy_pass http://nodes;
    }

}
```

> Tips

- nginx -t 
- nginx -s reload
