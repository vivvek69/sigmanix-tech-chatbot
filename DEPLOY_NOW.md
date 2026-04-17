# 🚀 DEPLOYMENT GUIDE - Sigmanix Tech Chatbot

## Status: ✅ READY FOR PRODUCTION DEPLOYMENT

**Repository:** https://github.com/vivvek69/sigmanix-tech-chatbot

---

## 🎯 ONE-CLICK DEPLOYMENT OPTION

### **Option 1: Deploy to Render (RECOMMENDED - Most Reliable ⭐)**

**Time Required:** 5 minutes  
**Cost:** FREE (24/7 hosting included)  
**Result:** Public URL like: `https://sigmanix-chatbot.onrender.com`

#### Steps:

1. **Go to:** https://render.com
2. **Click:** Sign up (free, no credit card needed)
3. **Choose:** GitHub login (easiest)
4. **Click:** "New +" → "Web Service"
5. **Select:** "Connect account" → GitHub
6. **Choose:** `vivvek69/sigmanix-tech-chatbot`
7. **Configure:**
   - Name: `sigmanix-chatbot`
   - Build Command: `pip install -r requirements.txt`
   - Start Command: `gunicorn chatbot_production:app`
8. **Add Environment Variable:**
   - Key: `GROQ_API_KEY`
   - Value: [Get from https://console.groq.com]
9. **Click:** "Create Web Service"
10. **Wait:** 3-5 minutes for deployment
11. **Done!** Your chatbot is live! 🎉

**Benefits:**
- ✅ Always on (no spin-down)
- ✅ Auto-scales with traffic
- ✅ Auto-deploys on GitHub push
- ✅ Custom domain support
- ✅ FREE tier forever

**Get Groq API Key:**
- Go to: https://console.groq.com
- Sign up free
- Create API key
- Copy to Render Environment Variables

---

## 📦 Option 2: Deploy to Replit (FASTEST - 2 Minutes)

**Time Required:** 2 minutes  
**Cost:** FREE (24/7 hosting included)  
**Result:** Public URL like: `https://[username]-sigmanix-chatbot.replit.dev`

#### Steps:

1. **Go to:** https://replit.com/new
2. **Click:** "Import from GitHub"
3. **Paste:** `vivvek69/sigmanix-tech-chatbot`
4. **Click:** Import
5. **Click:** 🔐 Secrets (lock icon)
6. **Add:** `GROQ_API_KEY = your_key_here`
7. **Click:** Run ▶️
8. **Done!** Your chatbot is live in 30 seconds! 🎉

---

## 📦 Option 3: Deploy to Your Own Server

### **Docker Deployment**

```bash
# Build Docker image
docker build -t sigmanix-chatbot .

# Run container
docker run -p 5000:5000 \
  -e GROQ_API_KEY=your_key \
  -e FLASK_ENV=production \
  sigmanix-chatbot
```

---

## 📦 Option 4: Deploy to Heroku

**Time Required:** 5 minutes  
**Cost:** $7/month (paid tier)  
**Result:** Public URL like: `https://sigmanix-chatbot.herokuapp.com`

```bash
# 1. Install Heroku CLI
# https://devcenter.heroku.com/articles/heroku-cli

# 2. Login
heroku login

# 3. Create Heroku app
heroku create sigmanix-chatbot

# 4. Add Groq API key
heroku config:set GROQ_API_KEY=your_key

# 5. Deploy
git push heroku main

# 6. Open app
heroku open
```

---

## 📦 Option 5: Deploy to Railway

**Time Required:** 5 minutes  
**Cost:** FREE tier (~$5 credits)  
**Result:** Public URL like: `https://sigmanix-chatbot.railway.app`

```bash
# 1. Go to: https://railway.app
# 2. Sign up (free)
# 3. Click: "New Project"
# 4. Select: "Deploy from GitHub repo"
# 5. Connect: vivvek69/sigmanix-tech-chatbot
# 6. Add Variable: GROQ_API_KEY = your_key
# 7. Click: Deploy
```

---

## 📦 Option 6: Deploy with Docker (VPS/Server)

**Time Required:** 10 minutes  
**Cost:** $5-20/month (depending on VPS)  
**Result:** Self-hosted on your server

```bash
# 1. SSH to your server
ssh user@yourdomain.com

# 2. Clone repository
git clone https://github.com/vivvek69/sigmanix-tech-chatbot.git
cd sigmanix-tech-chatbot

# 3. Create environment file
echo 'GROQ_API_KEY=your_key' > .env

# 4. Deploy with Docker Compose
docker-compose up -d

# 5. Access at: http://localhost:5000
```

---

## 🔧 Configuration

### **Environment Variables**

```env
# REQUIRED
GROQ_API_KEY=your_groq_api_key

# OPTIONAL
FLASK_ENV=production          # dev or production
PORT=5000                     # Server port
FLASK_SECRET_KEY=your_key     # Session encryption
REACT_DOMAINS=http://localhost:3000,https://yourdomain.com
DATABASE_PATH=chatbot_database.db
```

### **Database Setup**

Database is auto-initialized on first run:
- SQLite3 (included)
- Creates 4 tables automatically
- Stores conversations & feedback

---

## 🌐 Access Your Chatbot

### **After Deployment:**

1. **Web UI:** `https://your-domain.com` or `https://app.replit.dev`
2. **API:** `https://your-domain.com/api/chat`
3. **Admin Panel:** `https://your-domain.com/admin`

---

## 📊 Deployment Checklist

```
☐ Repository cloned/created
☐ .env file configured with GROQ_API_KEY
☐ requirements.txt installed
☐ data.txt (knowledge base) present
☐ Database initialized (automatic)
☐ Server running without errors
☐ UI accessible
☐ Chat endpoint responding
☐ CORS enabled for frontend
☐ Domain/SSL configured
☐ Monitoring set up
☐ Backups configured
```

---

## 📈 Performance & Monitoring

### **Monitor Your Deployment**

**Render:**
- Built-in analytics dashboard
- Real-time logs and error tracking
- Performance metrics visible
- Easy restart from dashboard

**Replit:**
- Built-in monitoring
- Performance metrics visible
- Easy restart from dashboard

**Custom Server:**
```bash
# Monitor server logs
tail -f chatbot.log

# Check CPU/Memory
htop

# Monitor Flask server
python -m pip install flask-talisman  # Add security headers
```

---

## 🐛 Troubleshooting

### **Issue: "GROQ_API_KEY not set"**
```
Solution: Add GROQ_API_KEY to .env or environment variables
```

### **Issue: "data.txt not found"**
```
Solution: Ensure data.txt is in same directory as chatbot_production.py
```

### **Issue: "Port already in use"**
```
Solution: Change PORT in .env or kill existing process
```

### **Issue: "CORS error"**
```
Solution: Update REACT_DOMAINS in .env with your frontend URL
```

---

## 📞 Support & Maintenance

### **Regular Tasks**

- **Daily:** Monitor logs for errors
- **Weekly:** Backup database
- **Monthly:** Update dependencies
- **Quarterly:** Review performance metrics

### **Backup Database**

```bash
# Backup
cp chatbot_database.db chatbot_database.db.backup

# Restore
cp chatbot_database.db.backup chatbot_database.db
```

---

## 🔒 Security Checklist

```
☐ HTTPS/SSL enabled
☐ Environment variables secured
☐ API keys not in code
☐ Input validation active
☐ Rate limiting enabled
☐ CORS properly configured
☐ Database backed up
☐ Logs monitored
```

---

## 📚 Documentation

- **[RENDER_DEPLOYMENT.md](./RENDER_DEPLOYMENT.md)** - Render detailed guide
- **[README.md](./README.md)** - Project overview
- **[QA_TESTING_REPORT.md](./QA_TESTING_REPORT.md)** - Test results

---

## ✅ READY TO DEPLOY

Your chatbot is **100% production-ready**:

- ✅ All files committed to GitHub
- ✅ Environment configured
- ✅ Dependencies specified
- ✅ Database schema ready
- ✅ API endpoints tested
- ✅ UI responsive

**Start deploying now! [Go to Render](https://render.com)**

---

**Last Updated:** April 17, 2026  
**Status:** Production Ready ✅  
**Repository:** https://github.com/vivvek69/sigmanix-tech-chatbot