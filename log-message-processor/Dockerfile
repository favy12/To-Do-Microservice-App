FROM python:3.6-slim

# Install GCC and other build tools
RUN apt-get update && apt-get install -y \
    gcc \
    build-essential \
    python3-dev \
 && rm -rf /var/lib/apt/lists/*

WORKDIR /app
COPY . .
RUN pip install --upgrade pip \
 && pip install -r requirements.txt
CMD ["python", "main.py"]
