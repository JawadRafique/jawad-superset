# Jawad Superset

A custom Superset deployment with embedded features and MySQL support.

## Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/JawadRafique/jawad-superset.git
   cd jawad-superset
   ```

2. **Set up environment variables**
   ```bash
   cp .env.example .env
   ```

3. **Edit the `.env` file with your database credentials**
   ```bash
   nano .env  # or use your preferred editor
   ```
   
   Update the `DATABASE_URL` with your MySQL connection details:
   ```
   DATABASE_URL=mysql://your_username:your_password@your_host:3306/superset
   ```
   
   Also update the admin credentials:
   - `SUPERSET_ADMIN_USERNAME`: Admin username
   - `SUPERSET_ADMIN_PASSWORD`: Admin password
   - `SUPERSET_ADMIN_EMAIL`: Admin email address

4. **Start the application**
   ```bash
   docker compose up
   ```

5. **Access Superset**
   - Open http://localhost:8088 in your browser
   - Login with the admin credentials from your `.env` file

## Configuration

The setup includes:
- **Embedded Superset**: Ready for iframe embedding
- **Template Processing**: Enabled for custom styling
- **MySQL Database**: Required for data persistence
- **Auto-initialization**: Creates admin user and sets up database on first run

## Environment Variables

Key variables to configure in `.env`:

```bash
# Admin user (created on first run)
SUPERSET_ADMIN_USERNAME=admin
SUPERSET_ADMIN_PASSWORD=your_secure_password
SUPERSET_ADMIN_EMAIL=admin@yourcompany.com

# Database connection (MySQL URL format)
DATABASE_URL=mysql://username:password@hostname:3306/superset

# Application settings
SUPERSET_ENV=development
SUPERSET_LOAD_EXAMPLES=no
SUPERSET_WEBSERVER_PREFIX=/dash
# generated via: openssl rand -base64 42
SECRET_KEY=your_generated_secret_key
```

## Requirements

- Docker & Docker Compose
- MySQL database (local or remote)
- Port 8088 available on your system

## Troubleshooting

- Ensure your MySQL database is accessible from the Docker container
- Check that the `superset` database exists in MySQL
- Verify all environment variables are set correctly in `.env`
- Check Docker logs: `docker compose logs -f`