## Setup
   
docker-compose up -d
docker-compose exec nginx apk add bash
docker-compose exec nginx bash
  apk add vim


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

nginx -t 
nginx -s reload