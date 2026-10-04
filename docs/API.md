# Plant Identification API Documentation

## Endpoints

### Authentication

#### Register User
```
POST /api/auth/register
{
  "email": "user@example.com",
  "password": "secure_password",
  "username": "plantlover"
}
```

#### Login
```
POST /api/auth/login
{
  "email": "user@example.com",
  "password": "secure_password"
}
```

### Plant Identification

#### Identify Plant
```
POST /api/identify
Content-Type: multipart/form-data

File: image.jpg (required)
Details:
{
  "latitude": 40.7128,
  "longitude": -74.0060,
  "season": "spring"
}
```

Response:
```json
{
  "id": "uuid",
  "species": {
    "scientific_name": "Rosa damascena",
    "common_name": "Damask Rose",
    "family": "Rosaceae",
    "confidence": 0.94,
    "alternatives": [
      {"name": "Rosa alba", "confidence": 0.03},
      {"name": "Rosa canina", "confidence": 0.02}
    ]
  },
  "care_tips": {
    "watering": "Keep soil moist but not waterlogged",
    "sunlight": "6-8 hours of direct sunlight",
    "temperature": "60-75°F (15-24°C)"
  },
  "timestamp": "2024-01-15T10:30:00Z"
}
```

#### Get Identification History
```
GET /api/identifications
Authorization: Bearer {token}
```

### Plant Database

#### Search Plants
```
GET /api/plants/search?q=rose&limit=10
```

#### Get Plant Details
```
GET /api/plants/{species_id}
```

### User Profile

#### Get User Profile
```
GET /api/users/profile
Authorization: Bearer {token}
```

#### Update User Profile
```
PUT /api/users/profile
Authorization: Bearer {token}
{
  "username": "newname",
  "bio": "Plant enthusiast"
}
```

## Response Codes

- `200`: Success
- `201`: Created
- `400`: Bad Request
- `401`: Unauthorized
- `404`: Not Found
- `429`: Rate Limited
- `500`: Server Error
