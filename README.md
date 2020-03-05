# Traefik v2 -  Jira

A Docker Compose configuration to run [Jira](https://www.atlassian.com/software/jira) behind a [Traefik](https://traefik.io/) reverse proxy.

## Usage

1. Clone this repository.
2. Modify the variables inside the .env file
3. Run `docker-compose up -d`.

## Installation

When setting up for the first time, you'll need to configure Jira. When asked what kind of environment you're setting up, specify it's a production environment. When asked to set up the database, specify you're using your own database and fill in the following details:
- Database type: `PostgreSQL`
- Hostname: `postgres`
- Port: `5432`
- Database: `jira`
- Username: `jira`
- Password: the password you set in `.env`
- Schema: `public`

