N8N with Traefik

Setup
To setup this project in production, first you need to copy the .env.example file as .env.

cp .env.example .env
Then, you need to open the new .env file and edit the following entries.

N8N_HOST=host.domain.com
ACME_EMAIL=name@email.com

These need to match your domain and have a valid email address for TTL certificate generation.

Start
After setup, to start n8n you need to start docker-compose by executing the following command in the current folder.

docker-compose up -d
To stop execution:

docker-compose stop
