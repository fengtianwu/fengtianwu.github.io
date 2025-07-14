+++
title = 'Cloudflare Tunnel'
date = 2024-08-08T09:13:04+08:00
draft = false
+++

# install cloudflare

```
$ brew install cloudflared
```

# login your count

```
$ cloudflared tunnel login
```

# create tunnel named *air*

```
$ cloudflared tunnel create air
```

# list tunnel

```
$ cloudflared tunnel list
```

# configure

```
tunnel: <Tunnel-UUID>
credentials-file: /root/.cloudflared/<Tunnel-UUID>.json
warp-routing:
    enabled: true
```


# add a route for tunnel air to IP/CIDR 10.0.0.0/8 


```
cloudflared tunnel route ip add 10.0.0.0/8 air

cloudflared tunnel route ip show

cloudflared tunnel run air

cloudflared tunnel info air

```
