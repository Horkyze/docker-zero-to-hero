# Docker Compose Todo App

This is a simple Todo application built with Ruby on Rails and PostgreSQL, containerized using Docker.

## Prerequisites

- Docker
- Docker Compose

## Getting Started


1. Start the application:
   ```
   docker-compose up -d
   ```
   This command builds the images (if not already built) and starts the containers in detached mode.

1. Run database migrations:
   ```
   docker-compose exec web bundle exec rails db:migrate
   ```
   This creates the database and runs any pending migrations.

1. Access the application:
   Open your web browser and go to `http://localhost:3003`

## Usage

- To create a new todo item, enter the title in the input field and click "Add Todo".
- To delete a todo item, click the "Delete" button next to the item.

## Stopping the Application

To stop the application and remove the containers:
```
docker-compose down
```

## Troubleshooting

If you encounter any issues:

1. Check if the containers are running:
   ```
   docker-compose ps
   ```

2. View the logs:
   ```
   docker-compose logs
   ```

3. If you make changes to the Dockerfile or docker-compose.yml, rebuild the images:
   ```
   docker-compose up -d --build
   ```

## File Structure

- `docker-compose.yml`: Defines the services, networks, and volumes for the application.
- `Dockerfile`: Contains instructions for building the Rails application image.
- `app/`: Contains the Rails application code.

## Development

To run commands in the Rails container:
```
docker-compose exec web bash
```

This opens a bash shell in the web container, where you can run Rails commands like:
- `rails console`
- `rails generate model ...`
- `rails db:migrate`

Remember to restart the application after making changes:
```
docker-compose restart web
```
