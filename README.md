# WordPress in a Docker makes me happy
Running WordPress with Docker

## Prerequisites
- Docker installed on your machine. You can download it from [here](https://www.docker.com/get-started).
- Basic knowledge of Docker and command line.
- A text editor to create and edit files.
## Steps
- Copy .env.example files and rename whithou the .example extension
- Fulfill the variables in the .env files
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
## Additional Notes
- You can customize the `docker-compose.yml` file to change ports, volumes, and other settings as needed.
- Make sure to back up your WordPress data regularly, especially if you're using this setup for production.
- For more advanced configurations, refer to the official Docker and WordPress documentation.
## License
This project is licensed under the Creative Commons Zero v1.0 Universal License. See the [LICENSE](LICENSE) file for details.
## Contact
daniel@wdreams.com  
Feel free to reach out if you have any questions or need assistance with this setup.
