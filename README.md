# Docker-compose file for forward HTTPS proxy Squid Proxy
<https://ubuntu.com/server/docs/proxy-servers-squid>

## Install
```
mkdir squid_proxy
cd squid_proxy
git clone https://github.com/movax01h/squid-forward-proxy.git .
docker compose up -d
```

## Authorization

Configured in squid.config at line 
```
auth_param basic program /usr/lib/squid/basic_ncsa_auth /etc/squid/passwords
```
Default username:pass is ```admin:admin```

Generate new pair with

```
sudo htpasswd -c ./volumes/passwords username
```


## Test connection
```
http_proxy=http://127.0.0.1:3128 curl -U 'admin:admin' example.com
```
