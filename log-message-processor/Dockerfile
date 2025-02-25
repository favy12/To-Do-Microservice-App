FROM python:3.9-slim

# Install build dependencies
RUN apt-get update && apt-get install -y \
    gcc \
    python3-dev \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app
COPY requirements.txt .

# Install without upgrading pip
RUN pip install --no-cache-dir -r requirements.txt

COPY . .
CMD ["python", "log_processor.py"]