# Use Python 3.13 official image
FROM python:3.13

# Set the working directory inside the container
WORKDIR /app

# Copy the application files
COPY flask_app.py requirements.txt /app/

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Expose port 5000
EXPOSE 5000

# Command to run the application
CMD ["python", "flask_app.py"]