# WordPress in a Docker makes me happy
Running WordPress with Docker

## Prerequisites
- Docker installed on your machine. You can download it from [here](https://www.docker.com/get-started).
- Basic knowledge of Docker and command line.
- A text editor to create and edit files.
- No service listening on ports 80 or 443. If not, reasign the exposed 'ports' for 'traefik' service on docker-compose.yml file, please.
## Steps
- Check & fulfill the variables in the example 'env' files:
  env-example
  marisadb-env-example
  traefik-env-example
  wordpress-env-example
- Execute `bash init.sh`
- Run the following command to start the containers:
```bash
docker compose up -d
```
- Open your web browser and go to `http://your.domain.com` to access your WordPress site.
- Follow the on-screen instructions to complete the WordPress setup.
## Stopping the Containers
To stop the containers, run the following command:
```bash
docker compose down
```
## Updating WordPress
To update WordPress, you can pull the latest image and recreate the containers:
```bash
docker compose down
docker compose pull
docker compose up -d
```
## Traefik Certs on Private Tunnels as Cloudflared
1. Go to 'docker-compose.yml'
2. Replace this line '- "--certificatesresolvers.letsencrypt.acme.tlschallenge=true"
' ...
3. For those ones:
- "--certificatesresolvers.letsencrypt.acme.dnschallenge=true"
- "--certificatesresolvers.letsencrypt.acme.dnschallenge.provider=cloudflare"
- "--certificatesresolvers.letsencrypt.acme.dnschallenge.delayBeforeCheck=0"
- "--certificatesresolvers.letsencrypt.acme.dnschallenge.delayBeforeCheck=30"
4. Add this envs in .traefik.env:
  CLOUDFLARE_EMAIL=your_cloudflare_email
  -> If you only have a global API KEY add this env:
  CLOUDFLARE_API_KEY=your_api_key
  -> If you could set or you have Token Keys for DNS Zone Edit, try one of those:
  CLOUDFLARE_DNS_TOKEN_KEY=your_api_key_for_dns_zone_edit
  CLOUDFLARE_ZONE_TOKEN_KEY=your_api_key_for_dns_zone_edit

## Additional Notes
- You can customize the `docker-compose.yml` file to change ports, volumes, and other settings as needed.
- Make sure to back up your WordPress data regularly, especially if you're using this setup for production.
- For more advanced configurations, refer to the official Docker and WordPress documentation.
## License
This project is licensed under the Creative Commons Zero v1.0 Universal License. See the [LICENSE](LICENSE) file for details.
## Contact
daniel@wdreams.com  
Feel free to reach out if you have any questions or need assistance with this setup.
