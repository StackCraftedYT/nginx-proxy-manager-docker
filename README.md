# Nginx Proxy Manager on Docker

A clean Docker Compose deployment for Nginx Proxy Manager, used to put self-hosted services behind HTTPS with automatic Let's Encrypt certificates.

## What this deploys

- Nginx Proxy Manager admin UI on port 81
- HTTP on port 80 and HTTPS on port 443
- Persistent data and certificate storage

## Quick start

```bash
git clone https://github.com/StackCraftedYT/nginx-proxy-manager-docker.git
cd nginx-proxy-manager-docker
docker network create web-net
docker compose up -d
```

Open the admin UI:

```
http://your-server-ip:81
```

Default login:

```
Email: admin@example.com
Password: changeme
```

Change the email and password immediately after first login.

## Add a proxy host

1. Hosts, Proxy Hosts, Add Proxy Host.
2. Domain: your domain.
3. Scheme: http.
4. Forward hostname: your service container name or host IP.
5. Forward port: the service port.
6. Enable Block Common Exploits and Websockets Support.
7. SSL tab: Request a new SSL certificate, enable Force SSL and HTTP/2.
8. Save.

## Vaultwarden example

If Vaultwarden runs in the same Docker network, forward to:

```
Hostname: vaultwarden
Port: 80
```

If it is bound to the host, forward to:

```
Hostname: 127.0.0.1
Port: 8081
```

## Links

- GitHub: https://github.com/StackCraftedYT
- Tutorials: https://stackcrafted.org/tutorials/