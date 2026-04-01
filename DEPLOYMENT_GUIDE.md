# RWOOM App - Complete Deployment Guide

**For Complete Beginners (Zero Coding Knowledge)**

This guide walks you through launching RWOOM locally, on Vercel, creating an APK, and deploying to the Play Store.

---

## Table of Contents
1. [Local Setup & Launch](#local-setup--launch)
2. [Vercel Deployment](#vercel-deployment)
3. [APK Creation (Android)](#apk-creation-android)
4. [Play Store Deployment](#play-store-deployment)
5. [API Integrations](#api-integrations)
6. [Troubleshooting](#troubleshooting)

---

## Local Setup & Launch

### What You Need
- **Computer** (Windows, Mac, or Linux)
- **Git** (version control software)
- **Node.js** (JavaScript runtime)
- **Code Editor** (Visual Studio Code recommended)

### Step 1: Install Required Software

#### Windows/Mac/Linux - Install Node.js
1. Go to https://nodejs.org/
2. Click the **LTS (Long Term Support)** button
3. Download and run the installer
4. Follow the installation wizard (click "Next" for all defaults)
5. Restart your computer

#### Verify Installation
1. Open **Terminal** (Mac/Linux) or **Command Prompt** (Windows)
2. Type: `node --version`
3. You should see a version number (e.g., v20.10.0)

#### Install Git
1. Go to https://git-scm.com/
2. Download and install for your operating system
3. Use default settings during installation

### Step 2: Get the RWOOM Code

1. Open Terminal/Command Prompt
2. Navigate to where you want to save the project:
   ```bash
   cd Desktop
   ```
3. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/rwoom.git
   cd rwoom
   ```

### Step 3: Install Dependencies

1. In Terminal, make sure you're in the `rwoom` folder
2. Run:
   ```bash
   npm install
   ```
   This downloads all required packages (takes 2-5 minutes)

### Step 4: Set Up Environment Variables

1. In the `rwoom` folder, create a file named `.env.local`
2. Add these variables (ask your backend developer for the actual values):
   ```
   VITE_APP_ID=your_app_id_here
   VITE_OAUTH_PORTAL_URL=https://oauth.manus.im
   DATABASE_URL=your_database_url_here
   JWT_SECRET=your_jwt_secret_here
   ```

### Step 5: Start the Development Server

1. In Terminal, run:
   ```bash
   npm run dev
   ```
2. You'll see output like:
   ```
   ➜  Local:   http://localhost:3000/
   ```
3. Open your browser and go to: **http://localhost:3000/**
4. You should see the RWOOM app!

### Stop the Server
Press `Ctrl+C` in Terminal to stop the development server.

---

## Vercel Deployment

**Vercel** is a free hosting platform perfect for web apps. Your app will be live on the internet!

### Step 1: Create a Vercel Account

1. Go to https://vercel.com/
2. Click **Sign Up**
3. Choose **GitHub** (easier) or email signup
4. Follow the verification steps

### Step 2: Connect Your GitHub Repository

1. In Vercel dashboard, click **New Project**
2. Click **Import Git Repository**
3. Paste your GitHub repo URL
4. Click **Import**

### Step 3: Configure Environment Variables

1. In the project settings, go to **Environment Variables**
2. Add all variables from your `.env.local` file:
   - `VITE_APP_ID`
   - `VITE_OAUTH_PORTAL_URL`
   - `DATABASE_URL`
   - `JWT_SECRET`
3. Click **Save**

### Step 4: Deploy

1. Click **Deploy**
2. Wait 2-5 minutes for deployment to complete
3. You'll get a URL like: `https://rwoom-abc123.vercel.app`
4. Share this URL with anyone to access your app!

### Automatic Deployments
Every time you push code to GitHub, Vercel automatically deploys the latest version.

---

## APK Creation (Android)

An **APK** is an Android app file you can install on phones.

### Prerequisites
- Completed Vercel deployment (your web app must be live)
- Android phone or emulator
- Google Play Developer account ($25 one-time fee)

### Step 1: Convert Web App to APK

Use **PWA Builder** (easiest method for beginners):

1. Go to https://www.pwabuilder.com/
2. Enter your Vercel URL: `https://rwoom-abc123.vercel.app`
3. Click **Start**
4. Click **Build My PWA**
5. Go to **Android** section
6. Click **Download** to get the APK file

### Step 2: Test the APK

#### On Android Phone:
1. Download the APK file to your phone
2. Open the file manager
3. Find the APK file
4. Tap it to install
5. Allow installation from unknown sources if prompted
6. The app will install and appear on your home screen

#### On Windows/Mac (using Emulator):
1. Install **Android Studio**: https://developer.android.com/studio
2. Create a virtual device
3. Drag the APK into the emulator window
4. The app will install

### Alternative: Use Capacitor (Advanced)

If PWA Builder doesn't work:

1. In Terminal, run:
   ```bash
   npm install @capacitor/core @capacitor/cli
   npx cap init
   npm run build
   npx cap add android
   npx cap sync
   npx cap open android
   ```
2. Android Studio will open
3. Click **Build** → **Build Bundle/APK** → **Build APK**
4. Wait for build to complete
5. APK will be in `android/app/release/`

---

## Play Store Deployment

**Google Play Store** is where billions of people download Android apps.

### Step 1: Create Google Play Developer Account

1. Go to https://play.google.com/console/
2. Click **Create account**
3. Pay $25 one-time registration fee
4. Complete your developer profile

### Step 2: Create App Listing

1. In Play Console, click **Create app**
2. Fill in:
   - **App name**: RWOOM
   - **Default language**: English
   - **App or game**: App
   - **Free or paid**: Free
3. Click **Create**

### Step 3: Prepare App Information

Fill in these sections:

#### App Details
- **Short description** (80 characters): "Collaborative PDF reading with real-time discussions"
- **Full description** (4000 characters): Describe all features
- **Category**: Books & Reference

#### Graphics & Images
Upload:
- **App icon**: 512x512 PNG
- **Screenshots**: 2-8 screenshots (max 3072x1728)
- **Feature graphic**: 1024x500 PNG
- **Promo graphic**: 180x120 PNG

#### Content Rating
1. Fill out the content rating questionnaire
2. Google will assign a rating (Usually 3+ or 12+)

### Step 4: Upload APK

1. Go to **Release** → **Production**
2. Click **Create new release**
3. Upload your APK file
4. Add release notes: "Initial release"
5. Click **Review**

### Step 5: Review & Submit

1. Go to **App content** and verify all information
2. Check **Pricing & distribution**:
   - **Countries**: Select all or specific countries
   - **Content rating**: Should be auto-filled
   - **Permissions**: Review and accept
3. Click **Submit for review**

### Step 6: Wait for Approval

- **Review time**: 24 hours to 7 days
- Google reviews for:
  - Malware
  - Policy violations
  - Functionality issues
- You'll receive email notification when approved

### Step 7: Launch

Once approved:
1. Go to **Release** → **Production**
2. Click **Roll out to Production**
3. Choose rollout percentage (start with 5-10%)
4. Gradually increase to 100% over days/weeks
5. Your app is now on the Play Store!

---

## API Integrations

### Required APIs for RWOOM

#### 1. Google OAuth (Authentication)
- **Purpose**: User login with Google account
- **Setup**:
  1. Go to https://console.cloud.google.com/
  2. Create new project
  3. Enable Google+ API
  4. Create OAuth 2.0 credentials
  5. Add to `.env.local`:
     ```
     VITE_APP_ID=your_client_id
     VITE_OAUTH_PORTAL_URL=https://oauth.manus.im
     ```

#### 2. Google Drive API (PDF Upload)
- **Purpose**: Users upload PDFs from Google Drive
- **Setup**:
  1. In Google Cloud Console, enable Drive API
  2. Create service account
  3. Download credentials JSON
  4. Store securely in environment variables

#### 3. Firebase Realtime Database (Chat)
- **Purpose**: Real-time messaging between users
- **Setup**:
  1. Go to https://firebase.google.com/
  2. Create new project
  3. Enable Realtime Database
  4. Add Firebase config to `.env.local`:
     ```
     VITE_FIREBASE_API_KEY=your_key
     VITE_FIREBASE_PROJECT_ID=your_project
     ```

#### 4. Stripe (Optional - Payments)
- **Purpose**: Premium features or subscriptions
- **Setup**:
  1. Go to https://stripe.com/
  2. Create account
  3. Get API keys
  4. Add to `.env.local`:
     ```
     VITE_STRIPE_PUBLIC_KEY=your_public_key
     STRIPE_SECRET_KEY=your_secret_key
     ```

---

## Troubleshooting

### "npm: command not found"
- **Solution**: Node.js not installed. Go back to Step 1 and install Node.js

### "Port 3000 already in use"
- **Solution**: 
  ```bash
  # Kill the process using port 3000
  # Windows: netstat -ano | findstr :3000
  # Mac/Linux: lsof -i :3000
  ```

### App not loading on localhost
- **Solution**: 
  1. Make sure `npm run dev` is still running
  2. Check browser console for errors (F12)
  3. Clear browser cache (Ctrl+Shift+Delete)

### APK won't install on phone
- **Solution**:
  1. Enable "Unknown sources" in Settings → Security
  2. Check if phone has enough storage
  3. Try uninstalling previous version first

### Play Store rejection
- **Common reasons**:
  - Broken links or features
  - Misleading description
  - Policy violations
  - Fix issues and resubmit

### Vercel deployment fails
- **Solution**:
  1. Check build logs in Vercel dashboard
  2. Verify all environment variables are set
  3. Make sure `.env.local` is in `.gitignore`
  4. Push code to GitHub and redeploy

---

## Quick Reference Commands

```bash
# Start development server
npm run dev

# Build for production
npm run build

# Run tests
npm test

# Format code
npm run format

# Check for errors
npm run check
```

---

## Support & Resources

- **Documentation**: https://rwoom.gitbook.io
- **GitHub Issues**: https://github.com/yourusername/rwoom/issues
- **Discord Community**: https://discord.gg/rwoom
- **Email Support**: support@rwoom.app

---

## Security Checklist

Before deploying to production:

- [ ] All API keys are in `.env` files (not in code)
- [ ] Database has backups enabled
- [ ] SSL/HTTPS is enabled
- [ ] Rate limiting is configured
- [ ] User data is encrypted
- [ ] Privacy policy is published
- [ ] Terms of service are published
- [ ] GDPR compliance is verified

---

## Next Steps After Deployment

1. **Monitor Performance**
   - Use Vercel Analytics
   - Check Google Play Console stats
   - Monitor error rates

2. **Gather User Feedback**
   - Respond to Play Store reviews
   - Collect bug reports
   - Track feature requests

3. **Iterate & Improve**
   - Fix bugs from user reports
   - Add requested features
   - Optimize performance

4. **Marketing**
   - Share on social media
   - Write blog posts
   - Reach out to book communities
   - Get app reviews from tech blogs

---

## Estimated Timeline

| Phase | Time |
|-------|------|
| Local setup | 30 minutes |
| Vercel deployment | 15 minutes |
| APK creation | 20 minutes |
| Play Store setup | 1-2 hours |
| Play Store review | 24 hours - 7 days |
| **Total** | **2-3 days** |

---

**Good luck launching RWOOM! 🚀**
