# NGINX Docker Setup (with SSL, Load Balancing, and Flask Backend)

## How to Use

1. Unzip the file
2. Make sure your domain points to this server
3. Run the following to start all services:
   ```bash
   docker-compose up --build -d
   ```

4. To generate SSL certificate (replace `yourdomain.com`):
   ```bash
   docker-compose run --rm certbot certonly      --webroot -w /var/www/certbot      --email you@example.com      --agree-tos --no-eff-email      -d yourdomain.com
   ```

5. Restart nginx to apply SSL:
   ```bash
   docker-compose restart nginx
   ```

6. (Optional) Set up a CRON job to renew SSL every 12 hours:
   ```bash
   ./renew-cert.sh
   ```
