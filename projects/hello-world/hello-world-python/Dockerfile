# Base Image
FROM python:alpine3.10

# Working directory
WORKDIR /app

# Copy code from current directory to working directory
COPY . /app

RUN pip install -r requirements.txt

# Expose port
EXPOSE 5000

# Launch of the python application
CMD python ./launch.py

