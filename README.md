# Cloudflare SSH Action

Run a remote command over SSH through Cloudflare Access and Cloudflare Tunnel.

## Usage

```yaml
- uses: your-user/cloudflare-ssh-action@v1
  with:
    host: ${{ secrets.CI_DEPLOYMENT_HOST }}
    username: ${{ secrets.CI_RPI_USERNAME }}
    private-key: ${{ secrets.CI_RPI_SSH_KEY }}
    known-hosts: ${{ secrets.CI_RPI_SSH_KNOWN_HOSTS }}
    service-token-id: ${{ secrets.CF_ACCESS_CLIENT_ID }}
    service-token-secret: ${{ secrets.CF_ACCESS_CLIENT_SECRET }}
    command: docker exec idrive-backend python manage.py migrate
```

The Cloudflare Access application must have a `Service Auth` policy allowing the supplied service token.
