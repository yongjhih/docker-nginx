## Usage

```sh
wget https://github.com/yongjhih/docker-nginx/raw/master/docker-compose.yml
docker-compose up -d
```

## Live config

```sh
$ docker cp dockernginx_nginx_1:/etc/nginx/conf.d/default.conf default.conf
$ cat >> default.conf
server {
    listen       80;
    server_name  example.com;

    location / {
        proxy_pass "localhost:8080";
    }
}

$ docker cp default.conf dockernginx_nginx_1:/etc/nginx/conf.d/default.conf
$ docker exec -it dockernginx_nginx_1 kill -HUP 1 # restart nginx
```

## Dump

```sh
docker cp dockernginx_nginx_1:/etc/nginx/nginx.conf nginx.conf
docker cp dockernginx_nginx_1:/etc/nginx/conf.d/default.conf default.conf
```

## About this Repo

This is the Git repo of the official Docker image for [nginx](https://registry.hub.docker.com/_/nginx/). See the
Hub page for the full readme on how to use the Docker image and for information
regarding contributing and issues.

The full readme is generated over in [docker-library/docs](https://github.com/docker-library/docs),
specificially in [docker-library/docs/nginx](https://github.com/docker-library/docs/tree/master/nginx).

