# ⚡ Quick Start — MetaCH AI Website

Get your AI website up and running in 5 minutes!

---

## 🎯 5-Minute Setup

### Step 1: Clone Repository (1 min)

```bash
git clone https://github.com/your-username/AI-Website-Project.git
cd AI-Website-Project
```

### Step 2: Get API Key (2 min)

1. Go to [Anthropic Console](https://console.anthropic.com)
2. Click "Create Key"
3. Copy the key (save it somewhere safe)

### Step 3: Add API Key (1 min)

```bash
# Copy example env file
cp .env.example .env

# Edit .env with your favorite editor
# Add your Claude API key:
# CLAUDE_API_KEY=sk_your_key_here
```

### Step 4: Run Locally (1 min)

```bash
# Using Python
python -m http.server 8000

# Or using Node.js
npx http-server

# Visit: http://localhost:8000
```

✅ **Done!** Your website is now running locally!

---

## 🚀 Deploy to Production (5 minutes)

### Option A: GitHub Pages (Easiest)

```bash
# 1. Create GitHub repository
# 2. Push code
git add .
git commit -m "Initial commit"
git push origin main

# 3. Go to Settings → Pages → Deploy from 'main' branch
# 4. Your site is live at https://your-username.github.io
```

### Option B: Netlify (No-Code)

```
1. Go to netlify.com
2. Click "New site from Git"
3. Select your GitHub repository
4. Add environment variables:
   - CLAUDE_API_KEY=sk_...
5. Deploy!
```

### Option C: Vercel (Fastest)

```
1. Go to vercel.com
2. Import your GitHub repository
3. Add environment variables
4. Deploy!
```

---

## 📝 First Time Setup Checklist

- [ ] Cloned repository
- [ ] Got Claude API key
- [ ] Created `.env` file
- [ ] Added API key to `.env`
- [ ] Running locally
- [ ] Chat interface working
- [ ] Ready to deploy

---

## 🎮 Test the Chat

1. Go to `http://localhost:8000/chat.html`
2. Click Settings (⚙️) button
3. Paste your API key
4. Click a prompt button
5. See AI response!

---

## 📚 Learn the Code

### Read These Files First (in order)

1. **README.md** - Project overview
2. **index.html** - HTML structure
3. **css/style.css** - Basic styling
4. **js/main.js** - JavaScript basics
5. **chat.html** - Chat interface
6. **css/chat.css** - Chat styling

### Then Explore

- **css/advanced.css** - Advanced animations
- **js/advanced.js** - Advanced patterns
- **LEARNING_GUIDE.md** - Detailed explanations

---

## 🔧 Common Tasks

### Change Site Title

Edit `index.html`:
```html
<title>Your Project Name</title>
```

### Change Colors

Edit `css/style.css`:
```css
:root {
    --accent: #your-color-here;
    --gold: #another-color;
}
```

### Add New Page

1. Create `yourpage.html`
2. Copy structure from `index.html`
3. Update navigation links
4. Add to nav menu

### Deploy Updates

```bash
git add .
git commit -m "Description of changes"
git push origin main
# Automatically deployed!
```

---

## ⚠️ Common Issues & Fixes

### "API Key Error"
```
Fix: Make sure API key is in .env file
Verify: CLAUDE_API_KEY=sk_... (starts with sk_)
```

### "Styles not loading"
```
Fix: Check file paths in HTML
<link rel="stylesheet" href="css/style.css">
```

### "Chat not responding"
```
Fix: Check browser console (F12)
Verify: API key is correct
Check: Internet connection
```

### "GitHub Pages showing 404"
```
Fix: Settings → Pages → Deploy from 'main' branch
Make sure 'index.html' exists in root
```

---

## 📱 Test on Mobile

```bash
# Get your local IP
# Windows: ipconfig
# Mac/Linux: ifconfig | grep inet

# Then visit from mobile:
http://192.168.1.100:8000
```

---

## 🎓 Next Steps

After setup:

1. ✅ Read LEARNING_GUIDE.md
2. ✅ Modify the code
3. ✅ Add your own features
4. ✅ Deploy your version
5. ✅ Share with others

---

## 🆘 Need Help?

| Issue | Resource |
|-------|----------|
| API errors | [Claude API Docs](https://docs.anthropic.com) |
| HTML/CSS | [MDN Web Docs](https://developer.mozilla.org) |
| JavaScript | [JavaScript.info](https://javascript.info) |
| Git | [GitHub Help](https://help.github.com) |
| General | [Create an Issue](https://github.com/your-username/AI-Website-Project/issues) |

---

## 🎉 Congratulations!

You now have a production-ready AI website!

### What You Have:
✅ Modern AI chat interface
✅ Responsive design
✅ Production-ready code
✅ Learning materials
✅ CI/CD pipeline
✅ Easy deployment

### Next:
- Customize it
- Learn from it
- Share it
- Contribute to it

---

## 🚀 Advanced Setup

### Install Dependencies (Optional)

```bash
npm install
npm run dev
npm run test
```

### Build for Production

```bash
npm run build
# Creates optimized version
```

### Deploy with Custom Domain

1. Buy domain (Namecheap, Google Domains)
2. Add CNAME record pointing to your host
3. Update GitHub Pages / Netlify settings
4. Wait for DNS to propagate

---

## 📊 Project Structure

```
📁 AI-Website-Project/
├── 📄 index.html           ← Landing page
├── 📄 chat.html            ← Chat interface
├── 📄 about.html           ← About page
├── 📁 css/
│   ├── style.css          ← Main styles
│   ├── chat.css           ← Chat styles
│   └── advanced.css       ← Advanced effects
├── 📁 js/
│   ├── main.js            ← Core functionality
│   └── advanced.js        ← Advanced features
├── 📁 .github/workflows/
│   └── deploy.yml         ← Auto-deploy
├── 📄 package.json        ← Project config
├── 📄 README.md           ← Main docs
├── 📄 LEARNING_GUIDE.md   ← Learning materials
└── 📄 .env.example        ← Config template
```

---

## 💡 Pro Tips

### Keep API Key Safe
```
NEVER commit .env to Git!
Use environment variables in production
```

### Test Before Deploying
```bash
npm run test
npm run lint
```

### Monitor Performance
```
Use Chrome DevTools (F12)
Check Lighthouse score
Analyze bundle size
```

### Document Changes
```
Write clear commit messages
Update README when needed
Comment complex code
```

---

**You're all set! 🚀**

Built with ❤️ by **Kabi lash** • Powered by **Claude API**

---

## Questions?

- 📖 Read LEARNING_GUIDE.md
- 🐛 Check GitHub Issues
- 💬 Start a Discussion
- 🤝 Contribute improvements!
