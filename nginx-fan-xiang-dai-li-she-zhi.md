### Nginx 配置文件

```bash
# WebSocket 配置
map $http_upgrade $connection_upgrade {
    default upgrade;
    ''      close;
}

# 配置80端口
server {
    listen 80;

    set $root_path '/var/www/https_test';
    root $root_path;
    index index.php index.html index.htm;

    server_name api.dcloud.club;

    # 所有请求重定向到 https
    rewrite ^(.*)$  https://api.dcloud.club$1 permanent;

    # 设置代理
    location / {
        proxy_pass http://localhost:8091;
    }

    location ~* ^/(css|img|js|flv|swf|download|ico)/(.+)$ {
        root $root_path;
        expires 30d;
        add_header pragma public;
        add_header cache-control "public";
    }

    location ~* \.(gif|jpg|jpeg|png|htm|css|js|flv|ico|swf|eot)$ {
        expires 30d;
        add_header pragma public;
        add_header cache-control "public";
    }

}

server {
    listen 443;
    server_name api.dcloud.club;

    set $root_path '/var/www/https_test';

    ssl on;
    root /var/www/https_test;
    index index.html index.htm;
    ssl_certificate   /path/to/api.dcloud.club_bundle.crt;
    ssl_certificate_key  /path/to/api.dcloud.club.key;
    ssl_session_timeout 5m;
    ssl_ciphers ECDHE-RSA-AES128-GCM-SHA256:ECDHE:ECDH:AES:HIGH:!NULL:!aNULL:!MD5:!ADH:!RC4;
    ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
    ssl_prefer_server_ciphers on;
    
     # WebSocket 配置
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection $connection_upgrade;

    location ~* ^/(css|img|js|flv|swf|download|ico)/(.+)$ {
        root $root_path;
        expires 30d;
        add_header pragma public;
        add_header cache-control "public";
    }

    location ~* \.(gif|jpg|jpeg|png|htm|css|js|flv|ico|swf|eot)$ {
        expires 30d;
        add_header pragma public;
        add_header cache-control "public";
    }
}
```



