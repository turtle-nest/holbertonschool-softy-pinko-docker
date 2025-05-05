# 1. Base Image
FROM ubuntu:latest

# 2. Update APT Packages
RUN apt-get update

# 3. Upgrade Already Installed Packages
RUN apt-get upgrade -y

# Install Python3 and pip3
RUN apt-get install -y python3 python3-pip

# Remove EXTERNALLY-MANAGED if necessary
RUN rm -f /usr/lib/python*/EXTERNALLY-MANAGED || true

# Install Flask with pip3
RUN pip3 install flask

# Install Flask-cors with pip3
RUN pip3 install flask-cors

# Set working folder in image
WORKDIR /app

# Copy the Python file into the container
COPY ./api.py /app/api.py

# Run the Flask server
CMD ["python3", "api.py"]
