# Nginx Extended
**Nginx** bundle for **Sublime Text 2/3**. It is based on [brandonwamboldt/sublime-nginx](https://github.com/brandonwamboldt/sublime-nginx), because it broken eg `directive + new line`.

## Highlighting
![screenshot](/Readme/example.png)

## Snippets
### Snippet Triggers
#### bootstrap

```nginx
upstream backend {
    server 127.0.0.1:8080;
}
 
server {
    listen       80;
    server_name  test.com *.test.com;

    access_log   /var/nginx.acc.test.com.log;
    error_log    /var/nginx.err.test.com.log;
 
    # Static
    location /public { 
        expires 30d;
        root /apps/test.com/;
    }
 
    # Proxy
    location / {
        proxy_pass http://backend;
    }
}
```

#### gzip

```nginx
# GZIP
gzip      on;
gzip_vary on;

gzip_disable "MSIE [4-6]\.";
gzip_types text/plain 
           text/css 
           application/json 
           application/x-javascript 
           text/xml 
           application/xml 
           application/xml+rss 
           text/javascript 
           application/javascript;
# gzip_buffers 16 8k;
# gzip_length 20;
# gzip_http_version 1.1;
# gzip_proxied off;
# gzip_comp_level 1;
```

#### trust

```nginx
# Trust Proxy
add_header Host             $host;
add_header X-Real-IP        $remote_addr;
add_header X-Forwarded-For  $proxy_add_x_forwarded_for;
```

#### comment

```nginx
#####################################
# Comment
#####################################
```

#### upstream

```nginx
server 127.0.0.1:8080 weight=1 fail_timeout=5s max_fails=1 slow_start=5s backup;
```

***

## Authors

**Alexander Krivoshhekov**

+ [http://twitter.com/FlatDev](http://twitter.com/FlatDev)
+ [http://github.com/SuperPaintman](http://github.com/SuperPaintman)