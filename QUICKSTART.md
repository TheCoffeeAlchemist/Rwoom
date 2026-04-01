# RWOOM - Quick Start Guide

## 🚀 Get Started in 3 Steps

### Step 1: Install Dependencies
```bash
npm install
```

### Step 2: Set Up Environment
Create `.env.local` file:
```
VITE_APP_ID=your_app_id
VITE_OAUTH_PORTAL_URL=https://oauth.manus.im
DATABASE_URL=your_database_url
JWT_SECRET=your_jwt_secret
```

### Step 3: Run Locally
```bash
npm run dev
```

Visit: http://localhost:3000

---

## 📱 Features

- **Explore Rooms**: Browse collaborative reading sessions
- **Join Rooms**: Read PDFs together with real-time chat
- **Friends**: Connect with other readers
- **Direct Messages**: Chat 1-on-1 with friends
- **Profile**: Manage your reading preferences

---

## 🌐 Deploy to Vercel

```bash
git push origin main
```

Vercel automatically deploys on every push!

---

## 📦 Build for Production

```bash
npm run build
npm run start
```

---

## 🧪 Run Tests

```bash
npm test
```

---

## 📚 Full Documentation

See `DEPLOYMENT_GUIDE.md` for:
- Local setup details
- Vercel deployment
- APK creation
- Play Store submission
- API integrations

---

## 🐛 Troubleshooting

**Port 3000 already in use?**
```bash
# Kill the process
lsof -i :3000 | grep LISTEN | awk '{print $2}' | xargs kill -9
```

**Dependencies issues?**
```bash
rm -rf node_modules package-lock.json
npm install
```

**Build fails?**
```bash
npm run check  # Check for TypeScript errors
npm run format # Format code
npm run build  # Try building again
```

---

## 📞 Support

- GitHub Issues: https://github.com/yourusername/rwoom/issues
- Email: support@rwoom.app
- Discord: https://discord.gg/rwoom

---

**Happy reading! 📖**
