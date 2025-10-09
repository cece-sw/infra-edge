# infra-edge
infra-edge runs a single Traefik reverse proxy for my Jelastic environment. It terminates TLS with Let’s Encrypt, forces HTTP→HTTPS, routes multiple Dockerized apps by hostname (prod + password-protected staging), and exposes a password-protected Traefik dashboard. Deployed from GitHub via Actions over SSH.

## infra-edge (Traefik on Jelastic)

A hardened, single-entry reverse proxy stack for all my Docker apps on Infomaniak Jelastic.
Features:
- Automatic TLS via **Let’s Encrypt**
- **Global HTTP→HTTPS** redirect
- Hostname routing for many apps
- **Staging** subdomains protected by **basic-auth + noindex**
- **Traefik dashboard** protected by password
- GitHub Actions deployment to Jelastic (SSH)

## Architecture
![Architecture](/assets/images/infra-edge-archi.drawio.png "Infra Archi")

All app stacks join the shared external Docker network traefik-proxy and declare Traefik labels.
