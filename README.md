# Django Docker Application

This project is a Django application configured to run within a Docker environment. It includes a setup for vulnerability testing using Nikto.

## Project Structure

```
docker_django_nikto
├── app
│   ├── manage.py
│   ├── vulnerability_assessment
│   │   ├── static
│   │   │   └── css
│   │   │       └── style.css
│   │   ├── templates
│   │   │   └── index.html
│   │   ├── __init__.py
│   │   ├── settings.py
│   │   ├── urls.py
│   │   └── views.py
│   │   └── wsgi.py
├── db
│   └── conf
│   └── data
├── env
│   └── Dockerfile
│   └── .env
├── docker-compose.yml
├── requirements.txt
└── README.md
```

## Requirements

- Docker
- Docker Compose

## Setup Instructions

1. Clone the repository:
   ```
   git clone <repository-url>
   cd docker_django_nikto
   ```

2. Build the Docker image:
   ```
   docker-compose build
   ```

3. Run the application:
   ```
   docker-compose up
   ```

4. Access the application at `http://localhost:8000`.

## Usage

To perform vulnerability testing using Nikto, you can run the Nikto command within the Docker container. Ensure that Nikto is included in your `requirements.txt` file.

## Additional Information

For more details on how to use Django and Docker, refer to the official documentation for each technology.