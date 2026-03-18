# Odoo Docker

Docker Compose setup for running odoo locally.

- **Odoo**: Latest stable Odoo version
- **PostgreSQL**: Database for Odoo
- **Persistent volumes**: For data and configuration
- **Custom addons support**: Directory for additional modules

## Prerequisites

- [Docker](https://www.docker.com/get-started) (version 20.10 or later)
- [Docker Compose](https://docs.docker.com/compose/install/) (version 2.0 or later)

## Quick start

### 1. Clone or download the project

```bash
git clone <repository-url>
cd odoo-docker
```

### 2. Start the services

```bash
docker-compose up -d
```

This command will start the Odoo and PostgreSQL containers in the background.

### 3. Access Odoo

Once the containers are running, access Odoo in your browser:

**URL**: http://localhost:8069

**Default credentials**:

- Username: `admin`
- Password: `admin`

> ⚠️ **Important**: Change the default credentials after the first login for security.

## Project structure

```
odoo-docker/
├── docker-compose.yaml    # Docker Compose configuration
├── config/                # Odoo configuration files
├── addons/                # Custom Odoo modules
└── README.md              # This file
```

## Useful commands

- View container logs

```bash
# Logs for all services
docker-compose logs -f

# Logs for Odoo only
docker-compose logs -f odoo

# Logs for the database only
docker-compose logs -f db
```

- Stop the services

```bash
docker-compose stop
```

- Stop and remove the containers

```bash
docker-compose down
```

- Stop and remove containers, volumes, and networks

```bash
docker-compose down -v
```

> ⚠️ **Warning**: The previous command will delete all data stored in the volumes.

- Restart the services

```bash
docker-compose restart
```

- View container status

```bash
docker-compose ps
```

## Configuration

### Environment variables

Database credentials are configured in `docker-compose.yaml`:

- **Database**: `odoo`
- **User**: `odoo`
- **Password**: `odoo`

To change these credentials, edit `docker-compose.yaml` and update the corresponding environment variables.

### Volumes

The project uses two Docker volumes for data persistence:

- `odoo-data`: Stores Odoo data
- `db-data`: Stores PostgreSQL data

### Custom addons

You can add custom Odoo modules in the `addons/` directory. These modules will be automatically available in Odoo.


## Additional resources

- [Odoo official documentation](https://www.odoo.com/documentation)
- [Docker Compose documentation](https://docs.docker.com/compose/)
- [Odoo community forum](https://www.odoo.com/forum)
