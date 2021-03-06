# Let's Encrypt / Certbot on Raspberry Pi / ARM

### Supported tags and respective `Dockerfile` links
-	[`latest` (*Dockerfile*)](https://github.com/Tob1asDocker/rpi-certbot/blob/master/alpine.armhf.fork.Dockerfile) (*It always uses the latest [certbot version](https://github.com/certbot/certbot/releases/latest) with alpinelinux.*)
-	[`1.0.0` (*Dockerfile*)](https://github.com/Tob1asDocker/rpi-certbot/blob/master/alpine.armhf.Dockerfile) (*It is the latest [certbot version](https://pkgs.alpinelinux.org/package/v3.11/community/armhf/certbot) contained in alpinelinux.*)

### What is Certbot?
Certbot, previously the Let's Encrypt Client, is EFF's tool to obtain certs from Let's Encrypt, and (optionally) auto-enable HTTPS on your server. It can also act as a client for any other CA that uses the ACME protocol. 
> [certbot.eff.org](https://certbot.eff.org/) and [letsencrypt.org](https://letsencrypt.org/)

### How to use this image
* ``` $ docker pull tobi312/rpi-certbot ```
* ``` $ docker run --name certbot -it -v ./letsencrypt:/etc/letsencrypt -p 80:80 -p 443:443 --entrypoint='' tobi312/rpi-certbot sh -c 'certbot certonly --standalone -d __YOUR-DOMAIN__ -d www.__YOUR-DOMAIN__ --email __YOUR-EMAIL__ --text --agree-tos --server https://acme-v02.api.letsencrypt.org/directory --rsa-key-size 4096 --verbose --renew-by-default --standalone-supported-challenges http-01' ```
* Renew: ``` $ docker exec -it certbot sh -c 'certbot renew' ```

### This Image on
* [DockerHub](https://hub.docker.com/r/tobi312/rpi-certbot/)
* [GitHub](https://github.com/TobiasH87Docker/rpi-certbot)
