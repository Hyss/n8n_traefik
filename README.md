# N8N with Traefik

This was made using ideas from Danilo Pinotti [n8n-docker](https://github.com/danilopinotti/n8n-docker) and help from the Docker Expert ChatGPT. I haven't determined if I need postgreSQL or a Worker. If you need these please have a look at Danilo's page.
Additionally more environment variables may be required in the n8n container to allow the options you need. MCP servers for example require N8N_COMMUNITY_PACKAGES_ALLOW_TOOL_USAGE=true to be added. More information can be found on [Nerding-io's Github](https://github.com/nerding-io/n8n-nodes-mcp).

## Setup
To setup this project in production, first you need to copy the .env.example file as .env.
```
cp .env.example .env
```
Then, you need to open the new .env file and edit the following entries.
```
N8N_HOST=host.domain.com
ACME_EMAIL=name@email.com
```
These need to match your domain and have a valid email address for TTL certificate generation.

## Start
After setup, to start n8n you need to start docker-compose by executing the following command in the current folder.
```
docker-compose up -d
```
To stop execution:
```
docker-compose stop
```
## Production
To use in production, you only need to set the STAGE entry as production in the .env file and then restart the environment.

In the .env file:
```
STAGE=production
```
Commands to run after editing:
```
docker-compose stop
docker-compose up -d
```
Important: Only set as production after n8n works properly. Otherwise you may be blocked to obtain the SSL certificate at LetsEncrypt.
