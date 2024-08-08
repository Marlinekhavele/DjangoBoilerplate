# Django Boilerplate

A reusable boilerplate for starting new Django projects. This boilerplate includes basic configurations for static and media files, environment variable management, and optional Docker support.

## Features

- Django 3.2+
- Environment variable management with `python-decouple`
- Static and media file handling
- PostgreSQL database support
- Docker and Docker Compose setup for development
- Basic project structure with a `base` app for common templates and views

## Getting Started

### Prerequisites

- Python 3.8+
- `pip` and `virtualenv`
- Docker (optional, for containerized development)

### Setup

1. **Clone the repository**

    ```bash
    git clone https://github.com/Marlinekhavele/DjangoBoilerplate.git
    cd app
    ```

2. **Create and activate a virtual environment**

    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

3. **Install dependencies**

    ```bash
    pip install -r requirements.txt
    ```

4. **Create a `.env` file**

    ```bash
    cp .env.example .env
    ```

    Edit the `.env` file with your configuration settings.

5. **Run migrations**

    ```bash
    python manage.py migrate
    ```

6. **Create a superuser**

    ```bash
    python manage.py createsuperuser
    ```

7. **Run the development server**

    ```bash
    python manage.py runserver
    ```

### Configuration

- **Static files:** `STATIC_URL`, `STATICFILES_DIRS`, and `STATIC_ROOT` are set up in `settings.py`.
- **Media files:** `MEDIA_URL` and `MEDIA_ROOT` are set up in `settings.py`.

### Docker Setup

1. **Build and run the Docker containers**

    ```bash
    docker-compose up --build
    ```

2. **Run migrations inside the Docker container**

    ```bash
    docker-compose exec web python manage.py migrate
    ```

### Deployment

When you're ready to deploy, ensure all static files are collected:

```bash
python manage.py collectstatic