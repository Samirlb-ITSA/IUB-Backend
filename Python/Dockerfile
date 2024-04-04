FROM python:3.9

# Set working directory
WORKDIR /app

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1
ENV PYTHON_VERSION 3.11.5
ENV SECRET_KEY a629d8276b72b7c8cad02eee54b1dd2da059a37f782ff7fe517435ae6ef763f1
ENV ACCESS_TOKEN_EXPIRE_MINUTES 30
ENV ALGORITHM HS256
ENV REPORT_TEMPLATE_PATH /app/resources/


# Copy the rest of the application code into the container
COPY ./app .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt


# Add the app directory to the Python path
ENV PYTHONPATH "${PYTHONPATH}:/app"

# Expose port 8000
EXPOSE 8000

# Command to run your FastAPI application using Uvicorn
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]