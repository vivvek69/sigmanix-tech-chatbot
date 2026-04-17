# 🌟 RENDER DEPLOYMENT GUIDE - Sigmanix Tech Chatbot

## Status: ✅ READY FOR RENDER DEPLOYMENT

**Render URL:** https://render.com  
**Repository:** https://github.com/vivvek69/sigmanix-tech-chatbot  
**Estimated Time:** 5 minutes

---

## 🎯 STEP-BY-STEP DEPLOYMENT

### **Step 1: Sign Up on Render**

1. Go to: https://render.com
2. Click: **"Sign up"**
3. Choose: **"Sign up with GitHub"** (easiest)
4. Authorize Render to access your GitHub account
5. Done! ✅

---

### **Step 2: Create New Web Service**

1. Click: **"New +"** (top right)
2. Select: **"Web Service"**
3. Choose: **"Public Git repository"**
4. Paste: **`https://github.com/vivvek69/sigmanix-tech-chatbot.git`**
5. Click: **"Continue"**

---

### **Step 3: Configure Web Service**

Fill in the following:

**Basic Settings:**
- **Name:** `sigmanix-chatbot`
- **Environment:** Python 3
- **Region:** Choose closest to you (e.g., Oregon, Frankfurt)
- **Branch:** `main`

**Build & Deployment:**
- **Build Command:** `pip install -r requirements.txt`
- **Start Command:** `gunicorn chatbot_production:app`

**Instance Type:**
- Select: **"Free"** (recommended to start)
- Or upgrade to: **"Starter"** ($7/month) for better performance

---

### **Step 4: Add Environment Variables**

1. Click: **"Add Environment Variable"**

2. **First Variable:**
   - **Key:** `GROQ_API_KEY`
   - **Value:** [Get from step below]
   - Click: **"Add"**

3. **Optional Variables:**
   - `FLASK_ENV` = `production`
   - `FLASK_SECRET_KEY` = [generate random string]

---

### **Step 5: Get Your Groq API Key**

Before clicking "Deploy", you need your API key:

1. Open new tab: https://console.groq.com
2. Sign up (free)
3. In Dashboard:
   - Click: **"API Keys"**
   - Click: **"Create New API Key"**
   - Copy the key
4. Return to Render
5. Paste key in `GROQ_API_KEY` field

---

### **Step 6: Deploy!**

1. Click: **"Create Web Service"**
2. Render will:
   - Build your application
   - Install dependencies
   - Start your server
   - Assign public URL

3. **Wait:** 3-5 minutes for first deployment

---

### **Step 7: Access Your Chatbot**

After deployment:

1. Render dashboard shows: **"Service is live"** ✅
2. Your URL appears in top section: `https://sigmanix-chatbot.onrender.com`
3. Click the URL to open your chatbot
4. **Share with anyone!** 🌐

---

## ✅ WHAT YOU GET

- ✅ **Live URL:** `https://sigmanix-chatbot.onrender.com`
- ✅ **Always On:** 24/7 hosting
- ✅ **Auto-Deploy:** Updates on GitHub push
- ✅ **Custom Domain:** Add your domain anytime
- ✅ **SSL/HTTPS:** Automatic
- ✅ **Logs:** Real-time error tracking
- ✅ **Monitoring:** Built-in dashboard
- ✅ **Scaling:** Auto-scales with traffic

---

## 🔄 AUTO-DEPLOYMENT FROM GITHUB

After initial setup, every push to `main` branch auto-deploys:

```bash
git add .
git commit -m "Update chatbot features"
git push origin main
# Render automatically redeploys!
```

---

## 📊 RENDER DASHBOARD

After deployment, use Render dashboard to:

1. **View Logs:** Real-time server output
2. **Monitor:** CPU, memory, bandwidth usage
3. **Restart:** Manual restart if needed
4. **Settings:** Update environment variables
5. **Connect Domain:** Add custom domain

---

## 🐛 TROUBLESHOOTING

### **Issue: "Build failed"**
```
Solution: 
1. Check logs for error messages
2. Verify requirements.txt is in root directory
3. Ensure data.txt exists
4. Check GROQ_API_KEY is set
```

### **Issue: "Service not starting"**
```
Solution:
1. Check Start Command: gunicorn chatbot_production:app
2. Verify GROQ_API_KEY environment variable is set
3. Check logs for Python errors
```

### **Issue: "502 Bad Gateway"**
```
Solution:
1. Service might still be starting (wait 1-2 min)
2. Check if chatbot_production.py has errors
3. Ensure port 5000 binding is correct
```

### **Issue: "CORS error"**
```
Solution:
1. Check chatbot_production.py CORS configuration
2. Add your frontend domain to REACT_DOMAINS
3. Update on Render dashboard
```

---

## 📱 MOBILE ACCESS

After deployment:

1. Get your URL: `https://sigmanix-chatbot.onrender.com`
2. Open on phone/tablet
3. Works perfectly on mobile! 📱
4. Share link with team

---

## 💰 PRICING

**Free Tier:**
- Cost: $0/month
- Always on: Yes (on Free instances, no auto-sleep)
- Compute: Shared
- Suitable for: Testing, demos, low-traffic

**Starter Tier:**
- Cost: $7/month
- Always on: Yes (guaranteed)
- Compute: Dedicated
- Suitable for: Production, reliability

---

## 🔐 SECURITY

Render provides:
- ✅ HTTPS/SSL automatic
- ✅ DDoS protection
- ✅ Environment variable encryption
- ✅ GitHub OAuth security
- ✅ Auto-backups

---

## 📈 MONITORING & LOGS

**View Logs:**
1. Render Dashboard → Your Service
2. Click: **"Logs"** tab
3. See real-time server output

**Monitor Metrics:**
1. Click: **"Metrics"** tab
2. View: CPU, Memory, Bandwidth usage
3. Track performance over time

---

## 🚀 NEXT STEPS

After deployment:

1. ✅ Test your chatbot: Ask questions
2. ✅ Share the URL with team
3. ✅ Set up custom domain (optional)
4. ✅ Monitor logs for errors
5. ✅ Add teammates as collaborators

---

## 🔗 USEFUL LINKS

- **Render Dashboard:** https://dashboard.render.com
- **Groq Console:** https://console.groq.com
- **Your Repository:** https://github.com/vivvek69/sigmanix-tech-chatbot
- **Render Docs:** https://render.com/docs

---

## 📞 SUPPORT

**For Render Issues:**
- Email: support@render.com
- Docs: https://render.com/docs

**For Chatbot Issues:**
- Check logs in Render dashboard
- Review chatbot_production.py for errors
- Test locally first: `python chatbot_production.py`

---

**🎉 YOUR CHATBOT IS NOW LIVE ON RENDER!**

**Your URL:** `https://sigmanix-chatbot.onrender.com`

Share it with your team and users! 🌐