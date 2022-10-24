# proxy-nginx
Repo containing docker-compose to deploy nginx in reverse proxy mode alongside Harness relay proxy to accept HTTPS connections on a server.

# Add certs
Place your required cert and private key in the reverseproxy/certs folder named `cert.crt` and `cert.key`
Alternatively you can generate some self signed certs below

# Generate certs
If you're generating self signed certs you can generate them using this command (or any equivalent you like)

```openssl req -x509 -sha256 -nodes -newkey rsa:2048 -days 365 -keyout reverseproxy/certs/cert.key -out reverseproxy/certs/cert.crt ```

# Running
1. Add your relay proxy details to the .env file.
2. Add your certs to the /certs folder as described ^
3. `docker-compose --env-file .env up  relay-proxy  nginx`

