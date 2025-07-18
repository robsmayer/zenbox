# Zenbox

This project consists of a Flask backend and a React frontend. The backend serves API endpoints and, in production, serves the React build. The frontend replaces the previous Streamlit UI and fetches data from Flask endpoints.

## Structure
- `/backend`: Flask API and static file server
- `/frontend`: React app (to be created with Vite)

## Development

### Backend
1. Install dependencies:
   ```bash
   pip install -r backend/requirements.txt
   ```
2. Run Flask server:
   ```bash
   python backend/app.py
   ```

### Frontend
1. Create the React app in `/frontend` (see below).
2. Start the React dev server:
   ```bash
   cd frontend
   npm install
   npm run dev
   ```

## Production
- Build the React app (`npm run build` in `/frontend`), then serve with Flask.

## API
- `GET /api/data` — returns device log data as JSON
- `POST /api/device/connected` — log device connection event
- `POST /api/device/disconnected` — log device disconnection event
- `GET /api/device/stats` — get aggregated connection statistics including total time and sessions

Device events are stored in `device_events.csv` with format:
```
timestamp,isConnected
2025-07-12 10:30,true
2025-07-12 10:45,false
```
