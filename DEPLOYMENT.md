# VEXA-RIGS Deployment Guide

## 🚀 Quick Deploy to GitHub Pages (Free)

### Step 1: Install Git
Download and install Git from: https://git-scm.com/downloads

### Step 2: Create GitHub Repository
1. Go to https://github.com and create a new repository
2. Name it `vexa-rigs` or `vexa-rigs-website`
3. Don't initialize with README (we already have one)

### Step 3: Initialize Local Repository
```bash
cd "d:\Projects\VEXA-RIGS"
git init
git add .
git commit -m "Initial commit - VEXA-RIGS PC building website"
```

### Step 4: Connect to GitHub
```bash
git remote add origin https://github.com/YOUR_USERNAME/vexa-rigs.git
git push -u origin main
```

### Step 5: Enable GitHub Pages
1. Go to your repository on GitHub
2. Click "Settings" → "Pages"
3. Under "Source", select "Deploy from a branch"
4. Select "main" branch and "/ (root)" folder
5. Click "Save"

Your site will be live at: `https://YOUR_USERNAME.github.io/vexa-rigs/`

---

## 🚀 Alternative: Deploy to Netlify (Recommended)

### Why Netlify?
- ✅ Free hosting
- ✅ Custom domain support
- ✅ HTTPS included
- ✅ Fast deployment
- ✅ Form handling (if needed later)

### Steps:
1. Go to https://netlify.com
2. Sign up/login with GitHub
3. Click "New site from Git"
4. Connect your GitHub repository
5. Deploy settings:
   - Build command: (leave empty - static site)
   - Publish directory: `.` (root directory)
6. Click "Deploy site"

Your site will be live instantly!

---

## 🚀 Backend Server Deployment

### Option 1: Railway (Easiest)
1. Go to https://railway.app
2. Connect your GitHub repo
3. Railway auto-detects Node.js/Python
4. Set environment variables for email credentials
5. Deploy!

### Option 2: Heroku
1. Install Heroku CLI
2. Login: `heroku login`
3. Create app: `heroku create vexa-rigs-api`
4. Set config: `heroku config:set EMAIL_USER=your@email.com`
5. Deploy: `git push heroku main`

### Option 3: DigitalOcean App Platform
1. Go to https://cloud.digitalocean.com
2. Create App Platform app
3. Connect GitHub repository
4. Configure environment variables
5. Deploy

---

## 🔧 Environment Variables for Backend

Add these to your hosting platform:

### For Node.js:
```
EMAIL_USER=your-email@gmail.com
EMAIL_PASS=your-gmail-app-password
ADMIN_EMAIL=admin@vexa-rigs.com
```

### For Python:
```
EMAIL_USER=your-email@gmail.com
EMAIL_PASS=your-gmail-app-password
ADMIN_EMAIL=admin@vexa-rigs.com
```

---

## 📝 Update Frontend URLs

After deploying backend, update `index.html`:

```javascript
// Change from:
fetch('http://localhost:3001/api/pc-quote-request', {

// To your production URL:
fetch('https://your-backend-url.com/api/pc-quote-request', {
```

---

## 🎯 Recommended Deployment Plan

1. **Frontend**: Netlify or GitHub Pages (free, instant)
2. **Backend**: Railway or Heroku (free tier available)
3. **Domain**: Buy a custom domain and connect to Netlify

---

## 🧪 Testing Checklist

- [ ] Frontend loads correctly
- [ ] PC builder questionnaire works
- [ ] Contact form submits successfully
- [ ] Backend receives emails
- [ ] Mobile responsive design
- [ ] All links work

---

## 💡 Pro Tips

- Use a custom domain for professionalism
- Set up Google Analytics for visitor tracking
- Add a contact form on the main site
- Consider adding a blog section later
- Set up monitoring for the backend API

Happy deploying! 🎉