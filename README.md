# KittySecurity DevOps

This repository contains the DevOps configuration and infrastructure files for the KittySecurity project, including Docker Compose setup, Nginx configuration, and environment variable templates.

## Project Structure
```
├── .env.example # Example environment variables 
├── .gitignore 
├── docker-compose.yaml # Docker Compose configuration 
├── erd.puml # Entity Relationship Diagram (PlantUML) 
├── LICENSE 
├── README.md 
└── conf/ 
  └── nginx.conf # Nginx reverse proxy configuration
```
## Services

- **nginx**: Acts as a reverse proxy for frontend and backend services.
- **postgres**: PostgreSQL database service.
- **backend**: KittySecurity backend API (see backend repo for details).
- **frontend**: KittySecurity frontend application (see frontend repo for details).

## Usage

1. **Configure Environment Variables**

   Copy `.env.example` to `.env` and fill in the required values:

2. **Start Services**

Run the following command to start all services:

```
docker compose up --build
```

## Nginx Configuration

The Nginx reverse proxy is configured in [conf/nginx.conf](conf/nginx.conf):

- Requests to `/` are proxied to the frontend.
- Requests to `/api/` are proxied to the backend.

## Database

The PostgreSQL service uses environment variables for configuration. Make sure to set `DB_USERNAME`, `DB_PASSWORD`, and `DB_NAME` in your `.env` file.

## Entity Relationship Diagram

The ERD for the project is defined in [erd.puml](erd.puml):

![ERD](https://github.com/user-attachments/assets/c86611d1-b016-4606-9666-51f355e41258)

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.