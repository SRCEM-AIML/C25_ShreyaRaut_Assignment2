# Use an official Python runtime as a parent image
FROM python:3.9

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app/

# Install dependencies
RUN pip install django

# Expose port 8000 for the application
EXPOSE 8000

# Define the command to run the app
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
