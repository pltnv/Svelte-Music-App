# Svelte Music App

Music streaming web application developed as a coursework project for Financial University.

## Description

Svelte Music App is a web application with Flask/Python backend and Svelte frontend. It allows users to browse a collection of music tracks, search songs by title or artist, and play music through a web player.

## Features

- Collection of 30 music tracks (Russian language)
- Search tracks by title or artist name
- Random tracks displayed on the main page
- Audio player with playback controls
- Sort search results by duration (ascending/descending)
- Responsive UI built with Svelte and Chota CSS

## Music Source

Music tracks are sourced from [Zaycev.net](https://zaycev.net) and cover images from Yandex Music. The audio files are loaded dynamically from external URLs provided by these services.

## Architecture

The project consists of two main parts:

### Backend (Python/Flask)
- Framework: Flask
- Database: SQLite
- ORM: SQLAlchemy
- CORS: Flask-CORS for cross-origin requests

### Frontend (Svelte)
- Framework: Svelte 3
- CSS Framework: Chota CSS (svelte-chota)
- Build Tool: Rollup
- State Management: Svelte Stores

## Installation & Running

### Requirements

- Python 3.7+
- Node.js 12+
- npm or yarn

### Backend

1. Navigate to backend directory:
```bash
cd backend
```

2. Install dependencies (virtual environment recommended):
```bash
pip install flask flask-sqlalchemy flask-cors
```

3. Start the server:
```bash
python start.py
```

Backend will be available at: `http://127.0.0.1:8000`

### Frontend

1. Navigate to frontend directory:
```bash
cd frontend
```

2. Install dependencies:
```bash
npm install
```

3. Start dev server:
```bash
npm run dev
```

Frontend will be available at: `http://localhost:5000`

### Production Build

To create a production build of frontend:

```bash
cd frontend
npm run build
npm run start
```

## API Endpoints

### GET `/musics`
Returns random tracks (limit: 9 tracks)

**Response:**
```json
[
  {
    "id": 1,
    "label": "Track title",
    "author": "Artist",
    "cover": "Cover URL",
    "src": "Audio URL",
    "duration": 267,
    "liked": false,
    "status": false
  }
]
```

### GET `/music/filter/<label>/`
Search tracks by title or artist

**Parameters:**
- `label` - search string (searches both title and artist)

**Response:** Array of track objects

## Data Model

### Track
- `id` (Integer) - unique identifier
- `label` (String) - track title
- `author` (String) - artist name
- `cover` (String) - cover image URL
- `src` (String) - audio file URL
- `duration` (Integer) - duration in seconds 
