## Build image
```
docker run -t container-tag-name:[version] .
```
## Config after docker run
After container was builed from this image we need to exec into it and make a bit config to make it works smoothly
Now you cannot start nginx service. So just make a bit config inside container
Change some lines in nginx.conf as below

```
vi /etc/nginx/nginx.conf

sendfile on => off
user www-data => user root
```

Stop current container and start it again. Now you can start/stop service nginx.
