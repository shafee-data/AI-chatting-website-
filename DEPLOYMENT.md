# 🚀 Deployment Guide — MetaCH AI Website

Complete instructions for deploying your AI website to production on GitHub Pages, Netlify, or Vercel.

---

## 📋 Pre-Deployment Checklist

- [ ] API key is secure (stored in environment variables, never in code)
- [ ] All sensitive data removed from git history
- [ ] `npm run build` passes without errors
- [ ] All links and assets working locally
- [ ] `.env` file is in `.gitignore`
- [ ] Repository is public (for GitHub Pages)
- [ ] Domain is ready (optional)

---

## 🐙 Option 1: GitHub Pages (FREE)

### Step 1: Create GitHub Repository

```bash
# Initialize git (if not already done)
git init

# Add remote
git remote add origin https://github.com/your-username/AI-Website-Project.git

# Create main branch
git checkout -b main

# Add files
git add .

# Commit
git commit -m "Initial commit: MetaCH AI Website v2.0"

# Push to GitHub
git push -u origin main
```

### Step 2: Enable GitHub Pages

1. Go to GitHub repository **Settings**
2. Navigate to **Pages** (left sidebar)
3. Under "Build and deployment", select:
   - **Source**: `Deploy from a branch`
   - **Branch**: `main` / `/(root)`
4. Click **Save**

### Step 3: Configure for Custom Domain (Optional)

1. Buy a domain (Namecheap, Google Domains, etc.)
2. Go to GitHub Pages settings
3. Under "Custom domain", enter your domain
4. Add DNS records to your domain registrar:

```
CNAME  www  your-username.github.io
A      @    185.199.108.153
A      @    185.199.109.153
A      @    185.199.110.153
A      @    185.199.111.153
```

### Step 4: Automatic Deployment

GitHub Pages automatically deploys on every push to `main`!

**Your site will be available at:**
```
https://your-username.github.io/AI-Website-Project
```

Or with custom domain:
```
https://yourdomain.com
```

### Update Site

```bash
# Make changes locally
echo "Updated content" >> index.html

# Commit and push
git add .
git commit -m "Update: improved UI"
git push origin main

# GitHub automatically deploys!
```

---

## 🌐 Option 2: Netlify (FREE - Easiest)

### Step 1: Connect GitHub to Netlify

1. Go to [netlify.com](https://netlify.com)
2. Click **Sign up** → **GitHub**
3. Authorize Netlify access to your GitHub
4. Click **New site from Git**
5. Select your repository

### Step 2: Configure Build Settings

```
Build command: (leave empty - static site)
Publish directory: . (or root)
```

### Step 3: Add Environment Variables

1. Go to **Site settings** → **Build & deploy** → **Environment**
2. Click **Edit variables**
3. Add:
   - **CLAUDE_API_KEY**: `sk_your_key...`
   - Any other env vars from `.env.example`

### Step 4: Deploy

Click **Deploy site** and wait for deployment to complete.

**Your site will be available at:**
```
https://your-site-name.netlify.app
```

### Connect Custom Domain

1. Go to **Site settings** → **Domain management**
2. Click **Add custom domain**
3. Follow instructions to update DNS

---

## 🚀 Option 3: Vercel (FREE - Fastest)

### Step 1: Connect to Vercel

1. Go to [vercel.com](https://vercel.com)
2. Click **Sign up** → **GitHub**
3. Click **Import Project**
4. Select your repository

### Step 2: Configure Project

```
Framework: Other
Root Directory: ./
```

### Step 3: Add Environment Variables

1. Go to **Settings** → **Environment Variables**
2. Add your secrets:
   - **CLAUDE_API_KEY**: `sk_your_key...`

### Step 4: Deploy

Click **Deploy** and your site goes live instantly!

**Your site will be available at:**
```
https://your-project-name.vercel.app
```

---

## 🔐 Environment Variables in Production

### GitHub Pages (Client-Side - UNSAFE)

GitHub Pages serves static files. **Never put API keys in client-side code.**

**Solution:** Use a serverless function or backend API.

### Netlify & Vercel (Secure)

These platforms support environment variables securely:

1. **Local development:**
   ```bash
   cp .env.example .env
   # Edit .env with your real API key
   ```

2. **Production (Netlify/Vercel):**
   - Add environment variables in platform dashboard
   - Never commit `.env` to git

### Using Backend API (Recommended)

Create a backend endpoint to handle API calls:

```javascript
// backend/api/chat.js (Node.js/Express)
const express = require('express');
const app = express();

app.post('/api/chat', async (req, res) => {
    const { message } = req.body;
    const apiKey = process.env.CLAUDE_API_KEY; // Secure!
    
    const response = await fetch('https://api.anthropic.com/v1/messages', {
        method: 'POST',
        headers: {
            'Content-Type': 'application/json',
            'x-api-key': apiKey
        },
        body: JSON.stringify({
            model: 'claude-opus-4-1',
            max_tokens: 1024,
            messages: [{ role: 'user', content: message }]
        })
    });
    
    const data = await response.json();
    res.json(data);
});

app.listen(3000, () => console.log('API running on port 3000'));
```

---

## 📝 GitHub Actions CI/CD Pipeline

Create `.github/workflows/deploy.yml`:

```yaml
name: Deploy MetaCH

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest
    
    steps:
      - uses: actions/checkout@v3
      
      - name: Setup Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18'
      
      - name: Install dependencies
        run: npm install
      
      - name: Run tests
        run: npm test
      
      - name: Deploy to GitHub Pages
        if: success()
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./
          cname: yourdomain.com  # Optional
```

---

## 🔍 Monitoring & Debugging

### Check Deployment Status

**GitHub Pages:**
```bash
git log --oneline -5
# View deployment in Actions tab
```

**Netlify:**
- Check **Deploys** tab for build logs
- Use `netlify logs` CLI command

**Vercel:**
- Check **Deployments** dashboard
- View build logs in real-time

### Common Issues & Solutions

| Issue | Solution |
|-------|----------|
| 404 errors | Ensure correct publish directory |
| Styles not loading | Check CSS file paths (relative vs absolute) |
| API calls fail | Verify API key in environment variables |
| Service Worker errors | Clear browser cache and rebuild |

---

## 🔄 Continuous Deployment Setup

### Auto-deploy on Push

All three platforms support auto-deployment:

```bash
# 1. Make changes
git add .
git commit -m "Update: new feature"

# 2. Push
git push origin main

# 3. Automatic deployment happens!
# Check status in platform dashboard
```

### Scheduled Deployments

For scheduled updates, use GitHub Actions:

```yaml
on:
  schedule:
    - cron: '0 0 * * *'  # Daily at midnight
```

---

## 📊 Performance Optimization for Production

### Minify & Bundle

```bash
# Install build tools
npm install --save-dev terser cssnano

# Minify JavaScript
npx terser js/main.js -o js/main.min.js -c -m

# Minify CSS
npx cssnano css/style.css -o css/style.min.css
```

### Enable Compression

Most CDNs enable Gzip automatically. Verify:

```bash
curl -I https://your-site.com/
# Look for: Content-Encoding: gzip
```

### CDN Configuration

Use Cloudflare (free) for additional performance:

1. Go to [cloudflare.com](https://cloudflare.com)
2. Add site and update nameservers
3. Enable:
   - Automatic compression
   - Browser caching
   - Image optimization

---

## 🎯 Domain Setup

### From Registrar to Vercel/Netlify

1. **Purchase domain** (Namecheap, GoDaddy, etc.)
2. **Point to hosting:**

**For Netlify:**
```
Create CNAME record:
www  →  your-site.netlify.app
```

**For Vercel:**
```
Create CNAME record:
www  →  cname.vercel-dns.com
```

### SSL Certificate

All platforms provide free SSL:
- GitHub Pages: Automatic ✅
- Netlify: Automatic ✅
- Vercel: Automatic ✅

---

## 📱 Mobile Testing

### Test on Real Devices

```bash
# Get local IP
ifconfig | grep inet

# Access from mobile:
# http://192.168.1.100:8000
```

### Browser DevTools

Press `F12` and toggle device toolbar to test responsive design.

---

## 🆘 Need Help?

- **GitHub Pages:** [docs.github.com/pages](https://docs.github.com/pages)
- **Netlify:** [netlify.com/docs](https://netlify.com/docs)
- **Vercel:** [vercel.com/docs](https://vercel.com/docs)
- **Claude API:** [docs.anthropic.com](https://docs.anthropic.com)

---

**🎉 Congratulations! Your MetaCH AI Website is now live!**

Built with ❤️ by **Kabi lash** • Powered by **Claude API**
