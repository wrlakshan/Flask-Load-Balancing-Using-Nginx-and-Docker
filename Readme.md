# Flask Load Balancing Using Nginx and Docker

This project demonstrates how to set up a Flask application with load balancing using Nginx and Docker. Follow the steps below to replicate the environment and deployment.

## Prerequisites

Before starting, ensure you have Docker and Docker Compose installed on your system. Additionally, Python and pip should be installed for initial setup and testing.

## Setup and Development

### Python and Virtual Environment

1. Install `pip` for Python 3, if not already installed:
    ```bash
    sudo apt install python3-pip
    ```

2. Install `virtualenv` using pip:
    ```bash
    pip install virtualenv
    ```

3. Check your Python 3 version:
    ```bash
    python3 --version
    ```

4. Create a Python virtual environment for the project:
    ```bash
    python3 -m venv env
    ```

5. Activate the virtual environment:
    ```bash
    source env/bin/activate
    ```

6. To check installed packages in the virtual environment:
    ```bash
    pip list
    ```

7. To export the current packages to a `requirements.txt` file:
    ```bash
    pip freeze > requirements.txt
    ```

8. Install packages from `requirements.txt`:
    ```bash
    pip install -r requirements.txt
    ```

9. Deactivate the virtual environment when done:
    ```bash
    deactivate
    ```

### Flask Application

1. Install Flask outside of the virtual environment to test the application globally (optional):
    ```bash
    pip install Flask
    ```

2. Run the Flask application (ensure you are in the directory containing `app/wsgi.py`):
    ```bash
    python3 app/wsgi.py
    ```

## Docker and Nginx for Load Balancing

### Setting Up Docker Containers

1. Start the containers in detached mode:
    ```bash
    docker-compose up -d
    ```

2. To bring down the containers:
    ```bash
    docker-compose down
    ```

3. To rebuild the containers without using cache:
    ```bash
    docker-compose build --no-cache
    ```

4. To start the containers with building images, without cache, and scaling the app service to 3 instances:
    ```bash
    docker-compose up -d --build --scale app=3
    ```

This setup ensures that your Flask application runs within Docker containers, and Nginx is used to distribute the load among multiple instances of your application, enhancing performance and reliability.

## Conclusion

Follow the steps outlined above to set up and deploy your Flask application with Nginx as the load balancer and Docker for containerization. This README provides a basic framework for setting up a development environment, with deployment leveraging Docker and Nginx for scalability and efficiency.
