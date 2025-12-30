# New Year Wishing Website for Varsha 🎉

A beautiful, interactive New Year wishing website with animations, AI-powered messages, and a romantic theme built for Varsha.

## Features

- ✨ **Interactive Envelope Opening**: 3D envelope animation to start the experience
- 🌟 **Starfield Animations**: Dynamic starfield that can form a heart shape
- ⏰ **Eternal Clock**: Timer showing time since the relationship began
- 💌 **AI-Powered Messages**: Generate personalized romantic messages using Google Gemini API
- 🔐 **Biometric Scanner**: Interactive fingerprint scanner to reveal a certificate
- 🚀 **Warp Speed Effect**: Stunning warp speed animation
- 🎵 **Background Music**: Ambient music player
- 📱 **Fully Responsive**: Works on desktop and mobile devices

## Tech Stack

- **Frontend**: HTML, CSS (Tailwind), JavaScript
- **Animations**: GSAP (GreenSock Animation Platform)
- **Backend API**: Vercel Serverless Functions
- **AI Integration**: Google Gemini API
- **Deployment**: Vercel

## Setup Instructions

### Local Development

1. Clone the repository:
```bash
git clone https://github.com/Manish0729/new-year-wishing.git
cd new-year-wishing
```

2. Install dependencies:
```bash
npm install
```

3. Open `index.html` in your browser or use a local server:
```bash
# Using Python
python -m http.server 8000

# Using Node.js (if you have http-server installed)
npx http-server
```

### Environment Variables

For the AI message generation feature to work, you need to set up a Google Gemini API key:

1. Get your API key from [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Add it to Vercel environment variables:
   - Go to Vercel Dashboard → Your Project → Settings → Environment Variables
   - Add `GEMINI_API_KEY` with your API key value
   - Select all environments (Production, Preview, Development)

See `ENV_SETUP.md` for detailed instructions.

## Deployment

### Deploy to Vercel

1. **Via Vercel CLI**:
```bash
npm install -g vercel
vercel
```

2. **Via GitHub Integration**:
   - Push this repository to GitHub
   - Go to [vercel.com](https://vercel.com)
   - Click "New Project"
   - Import your GitHub repository
   - Vercel will automatically detect the configuration
   - Add the `GEMINI_API_KEY` environment variable in project settings
   - Deploy!

### Vercel Configuration

The project includes `vercel.json` which configures:
- API routes (`/api/*`) to be handled by serverless functions
- All other routes to serve `index.html` (for SPA routing)

## Project Structure

```
.
├── index.html          # Main HTML file with all UI and scripts
├── api/
│   └── generate.js     # Serverless function for Gemini API integration
├── vercel.json         # Vercel deployment configuration
├── package.json        # Node.js dependencies
├── ENV_SETUP.md        # Environment variable setup guide
└── README.md           # This file
```

## Features Explained

### AI Message Generator
The website includes an AI-powered message generator that creates personalized romantic messages based on different moods:
- Romantic Poem
- Future Letter
- Funny Resolution
- Cosmic Compliment
- Love Forecast
- Emoji Love Letter

### Biometric Scanner
An interactive fingerprint scanner that requires holding for 2.5 seconds to reveal a certificate declaring Varsha as the "Love of My Life".

### Starfield Animations
- Normal mode: Falling stars
- Heart mode: Stars align to form a heart shape
- Warp mode: Warp speed effect with colorful streaks

## Customization

To customize for a different person:
1. Find and replace "Varsha" in `index.html`
2. Update the start date in the timer calculation (currently February 19, 2022)
3. Modify the timeline dates and messages
4. Update the envelope seal initial (currently "V")

## License

ISC

## Made With ❤️

Created with love for Varsha to celebrate the New Year 2026.

