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



##Installation
###Locally
   1. **Clone the Repository:**
    
        ```bash
        Copy
        Edit
        git clone <repository-url>
        cd flask-docker-app
        ```
    
   2. Set Up a Virtual Environment (Optional but Recommended):
    
        ```bash
        Copy
        Edit
        python -m venv venv
        source venv/bin/activate   # On Windows: venv\Scripts\activate
        ```
        
   3. **Install Dependencies:**
    
        ```bash
        Copy
        Edit
        pip install -r requirements.txt
        
        
   ## Running the Application Locally
        
        
    1. **Start the Flask Application:**
    
        ```bash
        Copy
        Edit
        python app.py
        ```
    
    2. **Access the Application:**
    
        Open your browser and visit http://127.0.0.1:5000
        
        

Deployment with Docker
Using Docker (Standalone Container)
Build the Docker Image:

bash
Copy
Edit
docker build -t flask-app .
Run the Container:

bash
Copy
Edit
docker run -p 5000:5000 flask-app
Access the Application:

Open your browser and visit http://localhost:5000

Using Docker Compose (Recommended)
Build and Start the Application:

bash
Copy
Edit
docker-compose up --build -d
Stop the Application:

bash
Copy
Edit
docker-compose down
Custom Configuration
The app can be modified to include more routes, logging, database connectivity, and additional configurations.

Modify app.py to add more functionality.

Update requirements.txt to include additional dependencies.

Customize docker-compose.yml to integrate other services (e.g., databases).

Known Issues
Port Conflicts: Ensure port 5000 is available before running the container.

Docker Build Issues: If the build fails, clear the cache with:

bash
Copy
Edit
docker system prune -a