# Vercel Deployment Guide

This guide will help you deploy your New Year Wishing website to Vercel.

## Prerequisites

- A GitHub account (already done - repo is at `Manish0729/new-year-wishing`)
- A Vercel account (sign up at [vercel.com](https://vercel.com) if you don't have one)
- A Google Gemini API key (for AI message generation feature)

## Step 1: Deploy to Vercel

### Option A: Deploy via Vercel Dashboard (Recommended)

1. **Go to Vercel Dashboard**
   - Visit [vercel.com](https://vercel.com)
   - Sign in with your GitHub account

2. **Import Your Project**
   - Click on "Add New..." → "Project"
   - You'll see a list of your GitHub repositories
   - Find and select `Manish0729/new-year-wishing`
   - Click "Import"

3. **Configure Project Settings**
   - **Framework Preset**: Select "Other" (or leave as auto-detected)
   - **Root Directory**: Leave as `./` (default)
   - **Build Command**: Leave empty (no build step needed)
   - **Output Directory**: Leave empty (serving static files)
   - Click "Deploy"

4. **Wait for Deployment**
   - Vercel will automatically deploy your project
   - You'll get a URL like `https://new-year-wishing-xxxxx.vercel.app`

### Option B: Deploy via Vercel CLI

1. **Install Vercel CLI** (if not already installed):
   ```bash
   npm install -g vercel
   ```

2. **Login to Vercel**:
   ```bash
   vercel login
   ```

3. **Deploy**:
   ```bash
   cd "/Users/manish./Desktop/untitled folder 2/New Year Wishing"
   vercel
   ```
   - Follow the prompts
   - Select your account
   - Choose "Link to existing project" or "Create new project"

## Step 2: Set Up Environment Variable (IMPORTANT)

For the AI message generation feature to work, you need to add your Google Gemini API key:

1. **Get Your Gemini API Key**:
   - Go to [Google AI Studio](https://makersuite.google.com/app/apikey)
   - Sign in with your Google account
   - Click "Create API Key"
   - Copy the API key

2. **Add to Vercel**:
   - Go to your Vercel project dashboard
   - Navigate to **Settings** → **Environment Variables**
   - Click "Add New"
   - **Name**: `GEMINI_API_KEY`
   - **Value**: Paste your Google Gemini API key
   - **Environments**: Select all (Production, Preview, Development)
   - Click "Save"

3. **Redeploy** (required after adding environment variables):
   - Go to the **Deployments** tab
   - Click the **⋯** (three dots) on your latest deployment
   - Click **Redeploy**
   - Or push a new commit to trigger automatic redeployment

## Step 3: Verify Deployment

1. **Check Your Live Site**:
   - Visit the URL provided by Vercel
   - Test the website functionality

2. **Test AI Features**:
   - Click on one of the AI message generator buttons
   - If you see generated messages, the API is working!
   - If you see fallback messages, check that:
     - Environment variable is set correctly
     - Deployment was redeployed after adding the variable

3. **Check API Endpoint**:
   - Visit `https://your-project-url.vercel.app/api/generate`
   - You should see a "Method not allowed" error (this is expected for GET requests)
   - The API only accepts POST requests from the frontend

## Step 4: Custom Domain (Optional)

1. **Add Custom Domain**:
   - Go to **Settings** → **Domains**
   - Enter your domain name
   - Follow Vercel's DNS configuration instructions

2. **Configure DNS**:
   - Add the CNAME or A records as instructed by Vercel
   - Wait for DNS propagation (can take a few minutes to 24 hours)

## Troubleshooting

### API Not Working

- **Check Environment Variables**: Ensure `GEMINI_API_KEY` is set correctly
- **Redeploy**: Environment variables require a redeployment to take effect
- **Check API Key**: Verify your Gemini API key is valid and active
- **Check Function Logs**: Go to **Deployments** → Click on deployment → **Functions** tab → Check logs

### Build Errors

- Check that `vercel.json` is in the root directory
- Verify that `api/generate.js` exists and has the correct format
- Check Vercel deployment logs for specific errors

### Static Files Not Loading

- Ensure `index.html` is in the root directory
- Check that all assets (CSS, JS) are properly referenced
- Verify that `vercel.json` routes are correct

## Automatic Deployments

Vercel automatically deploys your site when you push to GitHub:

- **Production**: Deploys when you push to `main` branch
- **Preview**: Creates preview deployments for pull requests

## Support

- [Vercel Documentation](https://vercel.com/docs)
- [Vercel Support](https://vercel.com/support)

## Your Project Links

- **GitHub Repository**: https://github.com/Manish0729/new-year-wishing
- **Vercel Dashboard**: https://vercel.com/dashboard

---

✅ **Ready to Deploy!** Follow the steps above and your New Year Wishing website will be live in minutes!

