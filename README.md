# infra-edge
infra-edge runs a single Traefik reverse proxy for my Jelastic environment. It terminates TLS with Let’s Encrypt, forces HTTP→HTTPS, routes multiple Dockerized apps by hostname (prod + password-protected staging), and exposes a password-protected Traefik dashboard. Deployed from GitHub via Actions over SSH.
