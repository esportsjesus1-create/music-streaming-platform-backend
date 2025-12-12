# Music Streaming Platform - Backend API

## Overview

This is the backend API for the Unified Music Streaming Platform. It provides RESTful endpoints to support the Next.js frontend application.

**Status**: Initial Setup
**Frontend**: Deployed at unified-music-app-fd5f18o8.devinapps.com

## Technology Stack

- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: MongoDB (recommended) or PostgreSQL
- **Authentication**: JWT (JSON Web Tokens)
- **File Storage**: AWS S3 or similar for music files
- **Caching**: Redis (recommended)

## Project Structure

```
music-streaming-platform-backend/
├── src/
│   ├── controllers/      # Route controllers
│   ├── models/          # Database models
│   ├── routes/          # API routes
│   ├── middleware/      # Custom middleware
│   ├── services/        # Business logic
│   ├── utils/           # Utility functions
│   └── config/          # Configuration files
├── tests/               # Test files
├── .env.example         # Environment variables template
├── .gitignore
├── package.json
└── server.js            # Entry point
```

## Required API Endpoints

Based on the frontend annotation, the following endpoints are required:

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout
- `GET /api/auth/me` - Get current user

### User Profile
- `GET /api/user/profile` - Get user profile
- `PUT /api/user/profile` - Update user profile
- `GET /api/user/stats` - Get user statistics
- `GET /api/user/recently-played` - Get recently played tracks

### Music Library
- `GET /api/library` - Get user's music library
- `POST /api/library/tracks/:id` - Add track to library
- `DELETE /api/library/tracks/:id` - Remove track from library

### Search & Discovery
- `GET /api/search` - Search tracks, artists, albums, playlists
- `GET /api/genres` - Get all genres
- `GET /api/trending/tracks` - Get trending tracks
- `GET /api/recommendations/playlists` - Get recommended playlists

### Artists
- `GET /api/artists` - Get all artists
- `GET /api/artists/:id` - Get artist details
- `GET /api/artists/popular` - Get popular artists
- `POST /api/artists/:id/follow` - Follow artist
- `DELETE /api/artists/:id/follow` - Unfollow artist

### Albums
- `GET /api/albums` - Get all albums
- `GET /api/albums/:id` - Get album details

### Tracks
- `GET /api/tracks` - Get all tracks
- `GET /api/tracks/:id` - Get track details
- `GET /api/tracks/:id/stream` - Stream track
- `POST /api/tracks/:id/play` - Record play count

### Playlists
- `GET /api/playlists` - Get user's playlists
- `POST /api/playlists` - Create playlist
- `GET /api/playlists/:id` - Get playlist details
- `PUT /api/playlists/:id` - Update playlist
- `DELETE /api/playlists/:id` - Delete playlist
- `POST /api/playlists/:id/tracks` - Add track to playlist
- `DELETE /api/playlists/:id/tracks/:trackId` - Remove track from playlist

### Favorites
- `GET /api/favorites` - Get user's favorite tracks
- `POST /api/favorites/:id` - Add track to favorites
- `DELETE /api/favorites/:id` - Remove track from favorites

### Social Features
- `GET /api/social/activity` - Get social activity feed
- `GET /api/social/friends` - Get friends list
- `POST /api/social/friends/:id` - Add friend
- `GET /api/social/messages` - Get messages

### Analytics
- `GET /api/analytics/dashboard` - Get analytics dashboard data
- `POST /api/analytics/events` - Track analytics events

## Setup Instructions

### Prerequisites
- Node.js 18+ installed
- MongoDB or PostgreSQL database
- Redis (optional, for caching)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/esportsjesus1-create/music-streaming-platform-backend.git
cd music-streaming-platform-backend
```

2. Install dependencies:
```bash
npm install
```

3. Create `.env` file:
```bash
cp .env.example .env
```

4. Configure environment variables in `.env`:
```
PORT=5000
NODE_ENV=development
DATABASE_URL=mongodb://localhost:27017/music-streaming
JWT_SECRET=your-secret-key
JWT_EXPIRE=30d
FRONTEND_URL=https://unified-music-app-fd5f18o8.devinapps.com
```

5. Run the development server:
```bash
npm run dev
```

## Development

### Scripts
- `npm start` - Start production server
- `npm run dev` - Start development server with hot reload
- `npm test` - Run tests
- `npm run lint` - Run linter

## Integration with Frontend

The frontend expects API endpoints at `/api/*`. Configure CORS to allow requests from:
- `https://unified-music-app-fd5f18o8.devinapps.com`
- `http://localhost:3000` (for local development)

## Next Steps

1. Set up Express server with basic routing
2. Configure database connection
3. Implement authentication system
4. Create data models
5. Implement API endpoints matching frontend requirements
6. Add input validation and error handling
7. Set up file upload for music streaming
8. Implement caching layer
9. Add API documentation (Swagger/OpenAPI)
10. Deploy to production

## Documentation

API documentation will be available at `/api/docs` once implemented using Swagger.

## License

MIT
