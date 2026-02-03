# Running the MySQL Container

1. Build the MySQL Docker image:
   docker build -f Dockerfile.mysql -t nnnikol/mysql-local:1.0.0 .

2. Run the MySQL container with a volume attached:
   docker run -d --name mysql-container -p 3306:3306 -v mysql-data:/var/lib/mysql nnnikol/mysql-local:1.0.0

# Running the App Container

1. Update the `DATABASES` configuration in `todolist/settings.py` with the IP address of the running MySQL container.

2. Build the application Docker image:
   docker build -t nnnikol/todoapp:2.0.0 .

3. Run the application container:
   docker run -d --name todoapp-container -p 8080:8080 nnnikol/todoapp:2.0.0

# Accessing the App

1. Open your browser and navigate to: http://localhost:8080

# Docker Hub Repositories

- MySQL Image: https://hub.docker.com/r/nnnikol/mysql-local
- Application Image: https://hub.docker.com/r/nnnikol/todoapp
