# 🎯 START HERE - PubkyLab Quick Navigation

Welcome to **PubkyLab** - your interactive Pubky SDK playground! 🚀

This guide will help you get started in the fastest way possible.

## ⚡ Fastest Path to Success

### 1️⃣ **Want to try it NOW?** (30 seconds)
Just open `pubkylab.html` in any modern browser. That's it!

### 2️⃣ **Want to deploy for sharing?** (5 minutes)
Read → [QUICKSTART.md](QUICKSTART.md)

### 3️⃣ **Want detailed deployment guide?** (10 minutes)
Read → [DEPLOYMENT.md](DEPLOYMENT.md)

### 4️⃣ **Want to understand everything?** (20 minutes)
Read → [README.md](README.md)

## 📁 File Guide - What Should I Read?

### Essential Files (Start Here)
| File | Purpose | Read Time | When to Read |
|------|---------|-----------|--------------|
| **START_HERE.md** | You are here! | 2 min | Right now |
| **QUICKSTART.md** | Get started fast | 3 min | Before deploying |
| **pubkylab.html** | The actual app | N/A | Just open it! |

### Documentation Files (Read as Needed)
| File | Purpose | Read Time | When to Read |
|------|---------|-----------|--------------|
| **README.md** | Complete docs | 15 min | To understand fully |
| **DEPLOYMENT.md** | Deploy guide | 10 min | When deploying |
| **PROJECT_SUMMARY.md** | Project overview | 10 min | For contributors |

### Configuration Files (Don't Need to Read)
| File | Purpose | 
|------|---------|
| **package.json** | NPM config |
| **vercel.json** | Vercel config |
| **.github/workflows/deploy.yml** | GitHub Actions |
| **.gitignore** | Git ignore rules |
| **LICENSE** | MIT License |
| **index.html** | Auto-redirect page |

## 🎓 Choose Your Path

### Path A: "Just Show Me!" (Learner)
1. ✅ Open `pubkylab.html` in browser
2. ✅ Click "Generate New User"
3. ✅ Click "Sign Up"
4. ✅ Play with Write/Read/List/Delete tabs
5. ✅ Check the logs
6. 🎉 You're done! You've learned Pubky interactively

### Path B: "I Want My Own Deployment" (Builder)
1. ✅ Read [QUICKSTART.md](QUICKSTART.md)
2. ✅ Choose platform (GitHub Pages or Vercel)
3. ✅ Follow the 5-minute guide
4. ✅ Share your deployed URL
5. 🎉 You've deployed a real app!

### Path C: "I Want to Contribute" (Developer)
1. ✅ Read [README.md](README.md) 
2. ✅ Read [PROJECT_SUMMARY.md](PROJECT_SUMMARY.md)
3. ✅ Examine `pubkylab.html` code
4. ✅ Make improvements
5. ✅ Submit PR
6. 🎉 You've contributed to Pubky!

## 🚀 Deployment Decision Tree

```
Need to deploy?
├─ Yes
│  ├─ Already on GitHub?
│  │  └─ Use GitHub Pages (read QUICKSTART.md)
│  └─ Want fastest deploy?
│     └─ Use Vercel (read QUICKSTART.md)
└─ No
   └─ Just testing locally?
      └─ Open pubkylab.html in browser
```

## ✨ What Can I Do With This?

PubkyLab lets you:
- ✅ **Test** Pubky SDK without writing code
- ✅ **Learn** how Pubky works interactively
- ✅ **Prototype** ideas before building apps
- ✅ **Debug** SDK issues visually
- ✅ **Share** examples with team
- ✅ **Demo** Pubky capabilities
- ✅ **Experiment** safely in staging environment

## 🎯 First Time User Journey

### Step 1: Open the App (10 seconds)
```bash
# Just double-click this file:
pubkylab.html
```

### Step 2: Generate User (5 seconds)
Click the big **"Generate New User"** button.
You'll see a public key appear.

### Step 3: Sign Up (10 seconds)
Click **"Sign Up"**.
Wait a few seconds. You'll see "Signed up & authenticated ✓"

### Step 4: Write Data (20 seconds)
1. Go to **Write** tab
2. Path: `/pub/example.com/test.json`
3. Type: `JSON`
4. Content: `{"hello": "world"}`
5. Click **"Write Data"**
6. See success message!

### Step 5: Read Data (10 seconds)
1. Go to **Read** tab
2. Address: `/pub/example.com/test.json`
3. Type: `JSON`
4. Click **"Read Data"**
5. See your data appear!

### Step 6: Celebrate! 🎉
You just:
- Created a Pubky user
- Stored data on a decentralized homeserver
- Read it back successfully

**Total time: ~1 minute**

## 🔧 Configuration Requirements

You will need to obtain from your homeserver provider:

**Homeserver Public Key** (z32 format)
- This identifies which homeserver you're connecting to
- Example format: `8pinxxgqs41n4aididenw5apqp1urfmzdztr8jt4abrkdn435ewo`

**Invitation Code** (if required)
- Some homeservers require invitation codes for new signups
- Contact your homeserver administrator if needed

**SDK Version**
```
@synonymdev/pubky@0.6.0-rc.6 (loaded from CDN)
```

Enter these in the UI when you open the app!

## 🆘 Quick Troubleshooting

### Problem: Page won't load
**Solution**: Use a modern browser (Chrome, Firefox, Safari, Edge)

### Problem: "Module not found"
**Solution**: Serve via HTTP server, not file://
```bash
python -m http.server 8000
```

### Problem: Signup fails
**Solution**: 
- Check internet connection
- Verify invitation code hasn't been used
- Wait a few seconds and try again

### Problem: Can't read my data
**Solution**:
- Make sure you signed up first
- Use correct path format: `/pub/...`
- Check activity logs for errors

## 🎓 Learning Resources

### Inside This Project
- 📖 [README.md](README.md) - Complete documentation
- 🚀 [QUICKSTART.md](QUICKSTART.md) - 5-minute guide  
- 🌐 [DEPLOYMENT.md](DEPLOYMENT.md) - Deploy guide
- 📊 [PROJECT_SUMMARY.md](PROJECT_SUMMARY.md) - Overview

### External Resources
- 🔗 [Pubky Core](https://github.com/pubky/pubky-core) - Source code
- 📚 [Pubky Docs](https://pubky.github.io/pubky-core/) - Documentation
- 💬 [Telegram](https://t.me/pubkycore) - Community chat
- 🌐 [Pubky.org](https://pubky.org) - Official website

## 💡 Pro Tips

1. **Enable Debug Logs** - Change log level to "debug" to see everything
2. **Watch the Console** - Open browser DevTools to see SDK logs
3. **Copy Addresses** - Save public addresses to test reading from anywhere
4. **Test Edge Cases** - Try empty paths, special characters, large files
5. **Read the Logs** - The activity log shows exactly what's happening

## 🎯 Your Next Steps

Choose what fits your needs:

### Just Exploring?
→ Open `pubkylab.html` and play around!

### Want to Deploy?
→ Read [QUICKSTART.md](QUICKSTART.md) next

### Building an App?
→ Read [README.md](README.md) for architecture details

### Contributing?
→ Read [PROJECT_SUMMARY.md](PROJECT_SUMMARY.md) first

## 🌟 Success Criteria

You'll know you're successful when:
- ✅ PubkyLab loads in your browser
- ✅ You can generate users
- ✅ You can sign up successfully  
- ✅ You can write and read data
- ✅ You understand the SDK better
- ✅ You can share your deployment URL (optional)

## 📞 Need Help?

1. **Check the logs** in the app
2. **Read the error message** - they're helpful!
3. **Try the troubleshooting section** above
4. **Ask in Telegram**: https://t.me/pubkycore
5. **Open an issue**: https://github.com/pubky/pubky-core/issues

## 🎉 Ready?

**Recommended path for most users:**

1. Read this file ✅ (you're doing it!)
2. Open `pubkylab.html`
3. Follow the "First Time User Journey" above
4. Come back and read [QUICKSTART.md](QUICKSTART.md) if you want to deploy

**Time investment**: 5 minutes to try, 10 minutes to deploy.

---

**You got this! Let's build something amazing with Pubky! 🚀**

Questions? Join us on [Telegram](https://t.me/pubkycore)!
