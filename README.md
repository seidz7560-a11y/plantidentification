# Plant Identification App

A plant identification application that leverages image recognition and AI to help users identify plants from photos.

## Features

- **Image Upload**: Upload plant photos for identification
- **AI Recognition**: Uses TensorFlow/PyTorch models for plant species detection
- **Plant Database**: Comprehensive database of plant species with details
- **Search History**: Track identified plants
- **Plant Care Tips**: Get care instructions for identified plants
- **REST API**: RESTful API for integration

## Tech Stack

### Backend
- Python (FastAPI)
- TensorFlow/PyTorch for ML models
- PostgreSQL for database
- Redis for caching

### Frontend
- React.js
- TypeScript
- Tailwind CSS

### Deployment
- Docker & Docker Compose
- GitHub Actions for CI/CD
- AWS/Heroku ready

## Project Structure

```
plantidentification/
├── backend/              # Python FastAPI backend
├── frontend/             # React frontend
├── ml/                   # Machine learning models
├── docker-compose.yml    # Docker orchestration
├── .github/              # GitHub Actions workflows
└── docs/                 # Documentation
```

## Getting Started

See [docs/SETUP.md](docs/SETUP.md) for detailed setup instructions.

## License

MIT
