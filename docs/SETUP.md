# Setup Guide for Plant Identification App

## Prerequisites

- Docker & Docker Compose
- Node.js 18+
- Python 3.10+
- Git

## Quick Start with Docker

```bash
# Clone the repository
git clone https://github.com/seidz7560-a11y/plantidentification.git
cd plantidentification

# Start all services
docker-compose up -d

# Wait for services to be healthy (about 30 seconds)
# Frontend: http://localhost:3000
# Backend: http://localhost:8000
# API Docs: http://localhost:8000/docs
```

## Local Development Setup

### Backend Setup

```bash
cd backend

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Download ML models
python download_models.py

# Run database migrations
alembic upgrade head

# Start development server
uvicorn main:app --reload
```

### Frontend Setup

```bash
cd frontend

# Install dependencies
npm install

# Start development server
npm start
```

## Environment Variables

Create `.env` files in backend and frontend directories:

### Backend `.env`
```
DATABASE_URL=postgresql://plantuser:plantpass123@localhost:5432/plantidentification
REDIS_URL=redis://localhost:6379/0
ML_MODEL_PATH=./models
API_PORT=8000
ENVIRONMENT=development
```

### Frontend `.env`
```
REACT_APP_API_URL=http://localhost:8000/api
```

## Database Setup

```bash
# Run migrations
cd backend
alembic upgrade head

# Seed sample data
python seed_database.py
```

## Testing

```bash
# Backend tests
cd backend
pytest

# Frontend tests
cd frontend
npm test
```

## API Documentation

Once the backend is running, visit:
- Swagger UI: http://localhost:8000/docs
- ReDoc: http://localhost:8000/redoc
