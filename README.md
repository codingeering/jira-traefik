# Traefik v2 -  Jira

A Docker Compose configuration to run [Jira](https://www.atlassian.com/software/jira) behind a [Traefik](https://traefik.io/) reverse proxy.

## Usage

1. Clone this repository.
2. Modify the variables inside the .env file
3. Run `docker-compose up -d`.

### Optional
Jira might encounter some permission issues for folders `/var/atlassian/jira` and `/opt/atlassian/jira` since the user "daemon" is the one running the jira instances and does not have permission to access these folders. In that case do the following:

4. Run `docker exec -it -user root <CONTAINER ID> /bin/sh`
5. Run `chown -R daemon:daemon /var/atlassian/jira`
6. Run `chown -R daemon:daemon /opt/atlassian/jira`
7. Run `docker-compose down`
8. Run `docker-compose up -d`

## Installation

When setting up for the first time, you'll need to configure Jira. When asked what kind of environment you're setting up, specify it's a production environment. When asked to set up the database, specify you're using your own database and fill in the following details:
- Database type: `PostgreSQL`
- Hostname: `postgres`
- Port: `5432`
- Database: `jira`
- Username: the user you set in the `.env`
- Password: the password you set in `.env`
- Schema: `public`

