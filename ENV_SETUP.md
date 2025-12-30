# Environment Variable Setup for Vercel

## Step 1: Add Environment Variable in Vercel

1. Go to your Vercel project dashboard
2. Navigate to **Settings** → **Environment Variables**
3. Add a new variable:
   - **Name:** `GEMINI_API_KEY`
   - **Value:** Your Google Gemini API key (the one that was previously hard-coded)
   - **Environment:** Select all (Production, Preview, Development)
4. Click **Save**

## Step 2: Redeploy

After adding the environment variable, you need to redeploy:

1. Go to **Deployments** tab
2. Click the **⋯** (three dots) on your latest deployment
3. Click **Redeploy**

Or simply push a new commit to trigger automatic deployment.

## How It Works

- The API key is now stored securely in Vercel's environment variables
- The frontend calls `/api/generate` (a serverless function)
- The serverless function has access to `process.env.GEMINI_API_KEY`
- The API key never appears in the browser or source code

## Security Notes

✅ API key is server-side only  
✅ No API key in HTML/JS source code  
✅ No API key exposed to browser  
✅ Works with Vercel's environment variable system

