FROM python:3.10-slim

WORKDIR /app

# Install system dependencies (needed for PDF processing later)
RUN apt-get update && apt-get install -y \
    build-essential \
    libpoppler-cpp-dev \
    pkg-config \
    python3-dev \
    && rm -rf /var/lib/apt/lists/*

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

# We will override this in docker-compose for dev
CMD ["python", "src/main.py"]