# 🚀 DEPLOYMENT GUIDE - Sigmanix Tech Chatbot

## Status: ✅ READY FOR PRODUCTION DEPLOYMENT

**Repository:** https://github.com/vivvek69/sigmanix-tech-chatbot

---

## 🎯 ONE-CLICK DEPLOYMENT OPTION

### **Option 1: Deploy to Replit (RECOMMENDED - Fastest)**

**Time Required:** 5 minutes
**Cost:** FREE (24/7 hosting included)
**Result:** Public URL like: `https://sigmanix-chatbot.replit.dev`

#### Steps:

1. **Go to:** https://replit.com
2. **Click:** Sign up (free)
3. **Choose:** GitHub login (easiest)
4. **Click:** + Create → Import from GitHub
5. **Paste:** `vivvek69/sigmanix-tech-chatbot`
6. **Click:** Import
7. **Click:** Secrets (lock icon)
8. **Add:** `GROQ_API_KEY = your_key_here`
9. **Click:** Run ▶️
10. **Done!** Your chatbot is live! 🎉

**Get Groq API Key:**
- Go to: https://console.groq.com
- Sign up free
- Create API key
- Copy to Replit Secrets

---

## 📦 Option 2: Deploy to Your Own Server

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

### **Traditional Hosting (Plesk/cPanel)**

```bash
# 1. SSH to your server
ssh user@yourdomain.com

# 2. Clone repository
git clone https://github.com/vivvek69/sigmanix-tech-chatbot.git
cd sigmanix-tech-chatbot

# 3. Create virtual environment
python3 -m venv venv
source venv/bin/activate

# 4. Install dependencies
pip install -r requirements.txt

# 5. Set environment variables
nano .env
# Add: GROQ_API_KEY=your_key

# 6. Run with Gunicorn (production)
gunicorn --bind 0.0.0.0:5000 chatbot_production:app

# 7. Set up domain
# Point your domain to server IP
# Configure SSL certificate
```

### **Heroku Deployment**

```bash
# 1. Install Heroku CLI
# https://devcenter.heroku.com/articles/heroku-cli

# 2. Login
heroku login

# 3. Create Heroku app
heroku create your-app-name

# 4. Add Groq API key
heroku config:set GROQ_API_KEY=your_key

# 5. Deploy
git push heroku main

# 6. Open app
heroku open
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

1. **Web UI:** `https://your-domain.com` or `https://yourapp.replit.dev`
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

- **[README.md](./README.md)** - Project overview
- **[REPLIT_QUICK_START.md](./REPLIT_QUICK_START.md)** - 5-minute Replit setup
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

**Start deploying now!**

---

**Last Updated:** April 17, 2026
**Status:** Production Ready ✅
**Repository:** https://github.com/vivvek69/sigmanix-tech-chatbot