# My Video Site 🎬

A full-featured video platform with user authentication, S3 storage, playlists, profiles, and real-time messaging.

## Features

- 🎥 **Video Upload & Playback** - Store up to 100+ videos on AWS S3
- 👤 **User Profiles** - Create profiles with bios and profile pictures
- 📺 **Playlists** - Organize videos into custom playlists
- 💬 **Messaging** - Real-time messaging between users
- 🔐 **Authentication** - Secure signup/login with JWT
- ⭐ **Social Features** - Follow users, like videos, comment
- 🎨 **Responsive Design** - Mobile-friendly interface
- 🐳 **Docker Support** - Containerized backend and database

## Tech Stack

### Frontend
- HTML5, CSS3, JavaScript (Vanilla)
- Responsive design
- GitHub Pages deployment

### Backend
- Node.js with Express
- MySQL database
- AWS S3 for video storage
- JWT authentication
- Docker & Docker Compose

## Quick Start

### Prerequisites
- Node.js 16+
- Docker & Docker Compose
- AWS S3 Account

### Local Development

1. **Clone and install**
```bash
git clone https://github.com/o0ashley920o/my-video-site.git
cd my-video-site
cd backend && npm install && cd ..
```

2. **Setup environment**
```bash
cd backend
cp .env.example .env
# Edit .env with your credentials
```

3. **Start with Docker**
```bash
docker-compose up -d
```

4. **Initialize database**
```bash
docker exec my-video-site-db mysql -u root -proot my_video_site < backend/scripts/init-database.sql
docker exec my-video-site-app npm run seed
```

5. **Access**
- Frontend: http://localhost:3000
- Backend: http://localhost:5000
- API Docs: http://localhost:5000/api/docs

## Project Structure

```
my-video-site/
├── public/                 # Frontend (GitHub Pages)
│   ├── index.html
│   ├── css/
│   ├── js/
│   ├── assets/
│   └── pages/
├── backend/               # Node.js backend
│   ├── config/
│   ├── routes/
│   ├── controllers/
│   ├── models/
│   ├── middleware/
│   ├── scripts/
│   ├── tests/
│   └── server.js
├── docs/                  # Documentation
├── .github/workflows/     # CI/CD
├── docker-compose.yml
└── Dockerfile
```

## Documentation

- [Setup Guide](docs/SETUP.md)
- [AWS S3 Setup](docs/AWS-S3-SETUP.md)
- [API Documentation](docs/API.md)
- [Database Schema](docs/DATABASE-SCHEMA.md)
- [Architecture](docs/ARCHITECTURE.md)

## Environment Variables

See `backend/.env.example` for required variables:
- JWT secrets
- AWS credentials
- Database connection
- Email service
- CORS origins

## Testing

```bash
cd backend
npm test
npm run test:coverage
```

## Deployment

### GitHub Pages (Frontend)
Automatically deployed on push to main branch via GitHub Actions.

### Backend (Heroku/AWS)
```bash
docker build -t my-video-site:latest .
docker push your-registry/my-video-site:latest
```

## API Routes

All API routes documented in `docs/API.md`

Key endpoints:
- Authentication: `/api/auth/*`
- Videos: `/api/videos/*`
- Users: `/api/users/*`
- Playlists: `/api/playlists/*`
- Messages: `/api/messages/*`
- Upload: `/api/upload/*`

## Contributing

1. Create a feature branch
2. Make your changes
3. Add/update tests
4. Submit a pull request

## License

MIT

## Author

Created by @o0ashley920o

## Support

For issues and questions, please create a GitHub Issue.

---

**Last Updated:** 2026-06-05