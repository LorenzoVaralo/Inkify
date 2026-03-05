# Inkify

A minimalist Spotify remote control with an e-ink/Kindle aesthetic. Control your music without distractions.

## Features

- Clean, e-ink inspired design (paper texture, serif fonts)
- Responsive layout for both portrait and landscape orientations
- Real-time sync with Spotify playback
- Playback controls (previous, play/pause, next)
- Progress bar and timestamps
- Shows active device name
- Automatic token refresh
- Works on mobile and desktop

## Setup

### 1. Create a Spotify App

1. Go to [Spotify Developer Dashboard](https://developer.spotify.com/dashboard)
2. Click "Create App"
3. Fill in the details:
   - App Name: `Inkify` (or anything you like)
   - App Description: `Spotify remote control`
   - Redirect URI: Your GitHub Pages URL (see step 3)
4. Select "Web API" when asked which APIs you'll use
5. Click "Save"
6. Copy your **Client ID** from the app settings

### 2. Configure the App

Open `app.js` and replace the Client ID if needed:

```javascript
const CLIENT_ID = 'your-client-id-here';
```

### 3. Deploy to GitHub Pages

1. Create a new GitHub repository named `inkify`
2. Push this code to the repository
3. Go to Settings > Pages > Source: `main` branch
4. Your app will be available at: `https://<username>.github.io/inkify/`

### 4. Add Redirect URI to Spotify

In your Spotify App settings, add your GitHub Pages URL as a Redirect URI:

```
https://<username>.github.io/inkify/
```

**Important:** Include the trailing slash!

## Local Development

For local testing, add `http://127.0.0.1:8000/` as an additional Redirect URI in Spotify, then:

```bash
cd inkify
python3 -m http.server 8000
```

Open <http://127.0.0.1:8000> in your browser.

## Usage

1. Open the app and click "Connect to Spotify"
2. Authorize the app with your Spotify account
3. Start playing music on any Spotify device (phone, desktop, web player)
4. Use the controls to pause, play, skip forward, or go back
5. The display updates automatically when you change tracks

## Requirements

- **Spotify Premium** is required for playback control
- Music must be playing on a Spotify device for controls to work

## Troubleshooting

**"No music playing" message:**

- Make sure Spotify is open and playing on a device

**Controls not working:**

- Spotify Premium is required
- Ensure the Spotify app is active (not just background)

**Authentication errors:**

- Verify the Redirect URI matches exactly (including trailing slash)
- Check that your Client ID is correct
- Make sure you're accessing via HTTPS (or localhost for development)

## License

MIT
