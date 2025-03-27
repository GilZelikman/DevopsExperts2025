# Flask Docker App

Flask Docker App is a simple Flask-based web application designed to demonstrate containerized deployment using Docker. It serves a basic "Hello, World!" message when accessed via a web browser or API call. The application is lightweight, easy to deploy, and structured for scalability.

## Features
🚀 **Lightweight Flask App**: A minimal Flask web server.

🐳 **Dockerized**: Easily containerized for streamlined deployment.

🔄 **Auto-Restart**: Configured with Docker Compose for automatic restarts.

🌍 **Accessible UI**: Can be accessed via any web browser or API client.

## Project Structure
```bash
flask-docker-app/
├── app.py                # Flask application
├── requirements.txt      # Python dependencies
├── Dockerfile            # Docker build instructions
├── docker-compose.yml    # Docker Compose configuration
└── README.md             # Documentation

```

## Installation
### Locally
   1. **Clone the Repository:**
    
        ```bash
        git clone https://github.com/GilZelikman/DevopsExperts2025/tree/42c05a1aed355048610811410ebcc3ffa840bc6b/Phase_1
        cd Phase_1
        ```
    
   2. Set Up a Virtual Environment (Optional but Recommended):
    
        ```bash
        python -m venv venv
        source venv/bin/activate   # On Windows: venv\Scripts\activate
        ```
        
   3. **Install Dependencies:**
    
        ```bash
        pip install -r requirements.txt
        ```
        
## Running the Application Locally
        
        
1. **Start the Flask Application:**
    
    ```bash
    python flask_app.py
    ```
    
2. **Access the Application:**
    
    Open your browser and visit http://127.0.0.1:5000
        
        

## Deployment with Docker

### Using Docker (Standalone Container)

1. **Build the Docker Image:**

     ```bash
    docker build -t flask-app .
    ```
   
2. **Run the Container:**
    ```bash
    docker run -p 5000:5000 flask-app
    ```
3. **Access the Application:**

    Open your browser and visit http://localhost:5000

### Using Docker Compose (Recommended)

1. **Build and Start the Application:**

    ```bash
    docker-compose up --build -d
    ```

2. **Stop the Application:**
    ```bash
    docker-compose down
    ```

## Custom Configuration
- The app can be modified to include more routes, logging, database connectivity, and additional configurations.
- Modify flask_app.py to add more functionality.
- Update requirements.txt to include additional dependencies.
- Customize docker-compose.yml to integrate other services (e.g., databases).

## Known Issues
- Port Conflicts: Ensure port 5000 is available before running the container.

- Docker Build Issues: If the build fails, clear the cache with:

```bash
docker system prune -a
```