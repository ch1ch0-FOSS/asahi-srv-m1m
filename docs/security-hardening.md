# Security Hardening Documentation

## Network Binding

### Forgejo (Git Service)
- **Previous**: Bound to all interfaces (`:::3000`)
- **Current**: Localhost only (`127.0.0.1:3000`)
- **Rationale**: Prevents direct external access; requires reverse proxy for remote connectivity
- **Verification**: `ss -tlnp | grep 3000` shows `127.0.0.1:3000`

### PostgreSQL
- **Binding**: Localhost only (default)
- **Socket**: `/var/run/postgresql`
- **Access**: Local Unix socket and `127.0.0.1:5432` only

### Vaultwarden (Password Manager)
- **Binding**: Check and document current state
- **Recommendation**: Localhost only, reverse proxy for HTTPS access

## Next Hardening Steps
- [ ] Bind Vaultwarden to localhost
- [ ] Set up reverse proxy (Caddy or nginx) for HTTPS
- [ ] Configure firewall rules
- [ ] Enable fail2ban for SSH

