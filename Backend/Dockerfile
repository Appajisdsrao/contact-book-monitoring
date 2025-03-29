# Use a Python base image
FROM python:3.9-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the application files
COPY . .

# Install dependencies including Gunicorn
RUN pip install --no-cache-dir -r requirements.txt gunicorn

# Expose the backend port
EXPOSE 5000

# Run the application with Gunicorn
CMD ["gunicorn", "-w", "4", "-b", "0.0.0.0:5000", "contact_book:app"]

