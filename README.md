# Vue & Laravel - Docker Repository

This repository contains a Dockerized setup for a project combining Vue.js (Quasar Framework) and Laravel.

- PHP: 8.2.8
- Vue.js: 3.4.18
- Quasar: 2.15.2
- Laravel: 10.48.7
- phpMyAdmin: 5.2.1
- MariaDB: 11.3.2

## Project Structure

The repository is structured as follows:

├── backend/<br>
│ ├── Dockerfile<br>
│ └── ...<br>
│ <br>
├── frontend/<br>
│ ├── Dockerfile<br>
│ └── ...<br>
│ <br>
├── docker/<br>
│ ├── mariadb/<br>
│ └── nginx/<br>
│ <br>
└── docker-compose.yml<br>


- The `backend/` directory contains the Laravel backend code, including the `app/` directory for Laravel application files, and a `Dockerfile` for building the backend Docker image.
- The `frontend/` directory contains the Vue.js frontend code, including the `public/` directory and a `Dockerfile` for building the frontend Docker image.
- The `docker/` directory contains subdirectories for Docker-related files, such as `mariadb/` for MariaDB configuration and `nginx/` for Nginx configuration.
- The `docker-compose.yml` file is responsible for defining and orchestrating the Docker containers.

## Getting Started

To run the project locally using Docker, follow these steps:

1. Clone the repository:

   ```bash
   git clone git clone [repository_URL] [directory_name]
   ```
2. Change into the project directory:

   ```bash
   cd [directory_name]
   ```
3. Build and start the Docker containers:

   ```bash
   docker-compose up -d
   ```

Frontend http://localhost:8080 <br>
Backend http://localhost:8000 <br>
API http://localhost:8000/api or http://localhost:8080/api<br>
phpMyAdmin http://localhost:8181 (root user without password) <br>

## Running Commands inside Laravel container

we must use a prefix
```bash
docker-compose exec backend
```

so, for example instead of
```bash
php artisan list
```

we will run the command

```bash
docker-compose exec backend php artisan list
```

## Running Commands inside Vue container

we must use a prefix
```bash
docker-compose exec frontend
```

so, for example instead of
```bash
quasar -v
```

we will run the command

```bash
docker-compose exec frontend quasar -v
```