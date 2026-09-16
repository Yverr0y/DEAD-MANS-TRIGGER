<div align="center">

<img width="100%" alt="DEAD MANS TRIGGER" src="https://capsule-render.vercel.app/api?type=waving&color=0:000000,100:627B29&height=220&section=header&text=DEAD%20MANS%20TRIGGER&fontSize=60&fontColor=ffffff&animation=twinkling&fontAlignY=35&desc=Web%20%7C%20Node.js%20%7C%20JavaScript%20%7C%20Demo&descSize=16&descAlignY=58"/>

`Web` [`Node.js`](https://nodejs.org/) [`JavaScript`](https://developer.mozilla.org/en-US/docs/Web/JavaScript) `Demo` - Educational dead-man-switch demonstration with a Node.js server, check-in timers and optional email delivery. See the documented security limitations.

[Project website / live view](https://deadmantriggers.com/)

[![Typing SVG](https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=20&pause=1000&color=627B29&center=true&vCenter=true&multiline=true&repeat=true&width=950&height=90&lines=Educational+dead-man-switch+demonstration+with+a+Node.js+server%2C+check-in...%3BWeb+%2F+Node.js+%2F+JavaScript+%2F+Demo)](https://git.io/typing-svg)

![Existing project screenshot or recording](deadman.png)

<br>

[![Project](https://img.shields.io/badge/Project-DEAD--MANS--TRIGGER-627B29?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Ringmast4r/DEAD-MANS-TRIGGER)
[![Format](https://img.shields.io/badge/Format-Node.js-000000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Ringmast4r/DEAD-MANS-TRIGGER/tree/main)

[![Stars](https://img.shields.io/github/stars/Ringmast4r/DEAD-MANS-TRIGGER?style=flat-square&color=627B29)](https://github.com/Ringmast4r/DEAD-MANS-TRIGGER/stargazers)
[![Forks](https://img.shields.io/github/forks/Ringmast4r/DEAD-MANS-TRIGGER?style=flat-square&color=627B29)](https://github.com/Ringmast4r/DEAD-MANS-TRIGGER/network/members)
[![Repo Size](https://img.shields.io/github/repo-size/Ringmast4r/DEAD-MANS-TRIGGER?style=flat-square&color=627B29)](https://github.com/Ringmast4r/DEAD-MANS-TRIGGER)
[![Last Commit](https://img.shields.io/github/last-commit/Ringmast4r/DEAD-MANS-TRIGGER?style=flat-square&color=627B29)](https://github.com/Ringmast4r/DEAD-MANS-TRIGGER/commits/main)

</div>

---

# ⚠️ Dead Man's Trigger

**A server-powered dead man's switch that automatically sends emails when you fail to check in.**

Unlike browser-only solutions, this actually works when you're incapacitated because the timer runs on a server with automatic email delivery.

---

<a id="-try-the-demo-first"></a>
## `> try_the_demo_first`

### 🌐 [Live Visual Demo](https://ringmast4r.github.io/DEAD-MANS-TRIGGER/)

**See what it looks like!** Visit the GitHub Pages demo for a visual preview (non-functional, just UI).

### 💻 Run Locally in Demo Mode (Functional)

**Want to see how it ACTUALLY works without setting up email?**

```bash
git clone https://github.com/Ringmast4r/DEAD-MANS-TRIGGER.git
cd DEAD-MANS-TRIGGER
npm install
npm start
```

Visit `http://localhost:3000` - the server automatically runs in **DEMO MODE** when no SendGrid API key is found.
The system logs what WOULD be sent to the console without actually sending emails. Perfect for learning and testing!

**For full email functionality**, see [Email Configuration](#-email-configuration) below or read [DEMO-MODE.md](DEMO-MODE.md).

---

<a id="-critical-security-warning"></a>
## `> critical_security_warning`

**⚠️ THIS IS AN EDUCATIONAL DEMONSTRATION PROJECT ⚠️**

**DO NOT deploy this code to production without implementing security measures first.**

### 🔴 Known Security Issues (By Design for Learning):

1. **No Authentication** - Anyone can access all API endpoints
2. **Data Exposure** - `/api/status` returns all trigger data publicly
3. **Open CORS** - Any website can make requests to the API
4. **No Rate Limiting** - Vulnerable to spam and abuse
5. **Unencrypted Database** - Secret messages stored in plaintext
6. **No Input Validation** - Accepts any data without sanitization

### ✅ Before Production Deployment, You MUST:

- [ ] Add authentication (API keys, login system, or IP whitelist)
- [ ] Sanitize `/api/status` to remove sensitive data from response
- [ ] Implement rate limiting to prevent abuse
- [ ] Restrict CORS to your domain only
- [ ] Add input validation and sanitization
- [ ] Encrypt sensitive database fields
- [ ] Add HTTPS enforcement
- [ ] Set up monitoring and logging
- [ ] Review the SECURITY-EVALUATION.md (if available)

### 📚 This Project Is For:

- ✅ Learning server-side timers and automation
- ✅ Understanding dead man's switch concepts
- ✅ Educational purposes and experimentation
- ✅ Local development and testing

### ❌ This Project Should NOT Be Used For:

- ❌ Production deployments (without security hardening)
- ❌ Storing truly sensitive information
- ❌ Life-critical situations
- ❌ Public-facing services (without authentication)

**For production use cases, consider professional services like Google Inactive Account Manager or implement the security measures listed above.**

---

<a id="-important-read-before-contributing"></a>
## `> important_read_before_contributing`

**ALL commits must be authored by ringmast4r only.**

See `COMMIT-RULES.md` for commit guidelines. Never include AI attribution or co-authorship tags in commits to this repository.

---

<a id="-screenshots"></a>
## `> screenshots`

**Main Interface - Setup Screen**

![Dead Man's Trigger - Main Interface](deadman.png)

**Armed & Counting Down**

![Dead Man's Trigger - Activated](activated.png)

---

<a id="-features"></a>
## `> features`

- ✅ **Server-side countdown** - Runs 24/7, even when your browser is closed
- ✅ **Automatic email sending** - No manual clicks required
- ✅ **File attachments** - Automatically emails files when triggered
- ✅ **Persistent storage** - SQLite database survives server restarts
- ✅ **Simple web interface** - Easy setup and check-in from any browser
- ✅ **Privacy-focused** - Success page hides sensitive data
- ✅ **SendGrid powered** - Reliable email delivery via Web API

---

<a id="-quick-start"></a>
## `> quick_start`

### Prerequisites

- Node.js v14+ ([Download](https://nodejs.org/))
- SendGrid account (free tier: 100 emails/day)

### Installation

```bash
# 1. Clone or download this repo
git clone https://github.com/Ringmast4r/DEAD-MANS-TRIGGER.git
cd DEAD-MANS-TRIGGER

# 2. Install dependencies
npm install

# 3. Configure email
cp .env.example .env
# Edit .env with your SendGrid API key

# 4. Start server
npm start

# 5. Open web interface
# Visit http://localhost:3000
```

---

<a id="-email-configuration"></a>
## `> email_configuration`

The server uses SendGrid Web API for reliable email delivery.

### Step 1: Sign Up for SendGrid

1. Go to [SendGrid Signup](https://signup.sendgrid.com/)
2. Free tier: 100 emails/day forever (no credit card)
3. Verify your email address

### Step 2: Create API Key

1. Go to [API Keys](https://app.sendgrid.com/settings/api_keys)
2. Click "Create API Key"
3. Name: "Dead Mans Trigger"
4. Permission: Full Access
5. Copy the API key

### Step 3: Authenticate Your Domain (CRITICAL)

**Why?** Without domain authentication, Gmail/Outlook may silently drop your emails.

1. Go to [Sender Authentication](https://app.sendgrid.com/settings/sender_auth)
2. Click "Authenticate Your Domain"
3. Enter your domain (e.g., `yourdomain.com`)
4. Add the DNS records to your domain provider (Cloudflare, GoDaddy, etc.)
5. Click "Verify" in SendGrid

### Step 4: Configure .env File

```env
SENDGRID_API_KEY=SG.your-api-key-here
SENDER_EMAIL=alerts@yourdomain.com
SENDER_NAME=Dead Mans Trigger
REPLY_TO_EMAIL=your-personal-email@example.com
```

**Important:**
- `SENDER_EMAIL` must use your authenticated domain
- `REPLY_TO_EMAIL` is where recipients' replies go (can be any email)

---

<a id="-how-to-use"></a>
## `> how_to_use`

### 1. Setup Trigger

- Open http://localhost:3000
- Click "SETUP TRIGGER"
- Set timer duration (e.g., 24 hours = check in daily)
- Add email recipients (comma-separated)
- Write your secret message
- Optional: Upload file, add URLs
- Click "ARM TRIGGER"

### 2. Check In Regularly

- Click "CHECK-IN / RESET" before timer expires
- Proves you're alive and resets countdown
- Can close browser - server keeps running!

### 3. What Happens When Triggered

- Server automatically sends emails to all recipients
- Includes your secret message
- Attaches any uploaded files
- Privacy-focused success page shows delivery stats (not sensitive data)

---

<a id="-testing"></a>
## `> testing`

Test with a 1-minute trigger:

```
Duration: 0.0167 hours (1 minute)
Recipients: your-email@example.com
Message: "This is a test"
```

Wait 1 minute → Check your email inbox!

---

<a id="-technical-details"></a>
## `> technical_details`

- **Backend:** Node.js + Express
- **Database:** SQLite
- **Email:** SendGrid Web API (@sendgrid/mail)
- **Scheduler:** node-cron (checks every 10 seconds)
- **Frontend:** Vanilla HTML/CSS/JavaScript

No frameworks, no build step - just simple reliable tech.

---

<a id="-project-structure"></a>
## `> project_structure`

```
DEAD-MANS-TRIGGER/
├── server.js             # Main server
├── index.html            # Web interface
├── package.json          # Dependencies
├── .env.example          # Email config template
├── COMMIT-RULES.md       # Git commit policy
├── .gitignore            # Protects sensitive files
└── deadman.db            # Database (auto-created)
```

---

<a id="-deployment"></a>
## `> deployment`

For 24/7 operation, deploy to cloud:

**Recommended Platforms:**
- **Render** - Free tier, easy setup
- **Railway** - Simple deployment
- **Heroku** - Free tier available
- **DigitalOcean** - VPS option

**Important:** Most cloud hosts block SMTP ports. This is why we use SendGrid Web API (HTTPS port 443) instead of SMTP.

### Quick Deploy to Render

1. Push code to GitHub
2. Sign up at [Render.com](https://render.com/)
3. New Web Service → Connect your repo
4. Add environment variable: `SENDGRID_API_KEY`
5. Deploy!

---

<a id="-important-notes"></a>
## `> important_notes`

### What This IS:

- ✅ A functional dead man's switch for personal use
- ✅ Great for education and understanding automation
- ✅ Reliable for non-critical scenarios

### What This ISN'T:

- ❌ Enterprise-grade security
- ❌ Encrypted data storage
- ❌ For life-critical situations

**For critical use cases:** Use professional services like Google Inactive Account Manager or legal document services.

---

<a id="-security--privacy"></a>
## `> security__privacy`

**Data Protection:**
- Email credentials stored in `.env` (gitignored)
- Database stored locally (unencrypted)
- Files stored as base64 (keep under 10MB)
- Anyone with server access can view data

**Privacy Features:**
- Success page shows recipient COUNT, not addresses
- Message LENGTH shown, not actual content
- File TYPE/SIZE shown, not file contents

**Recommendations:**
- Keep `.env` file private
- Don't commit `.env` to version control
- Use strong passwords for server access
- Consider encryption for sensitive data

---

<a id="-use-cases"></a>
## `> use_cases`

- Send important info to loved ones if you can't check in
- Educational project for learning timers and automation
- Backup system for critical information
- Reminder system with consequences

---

<a id="-license"></a>
## `> license`

MIT License - Use however you want!

---

<a id="-contributing"></a>
## `> contributing`

Pull requests welcome!

**Before contributing, read `COMMIT-RULES.md` for commit guidelines.**

Ideas for improvements:
- End-to-end encryption
- SMS notifications (Twilio)
- Web dashboard for multiple triggers
- Multi-user support
- Advanced scheduling

---

<a id="-documentation"></a>
## `> documentation`

- **[DEMO-MODE.md](DEMO-MODE.md)** - Complete guide to running in demo mode without email
- **[.env.example](.env.example)** - SendGrid configuration guide
- **[COMMIT-RULES.md](COMMIT-RULES.md)** - Git commit policy

---

<a id="-troubleshooting"></a>
## `> troubleshooting`

**Emails not arriving?**
1. Check SendGrid API key is correct
2. Verify domain authentication is complete
3. Check SendGrid Activity Feed for delivery status
4. Make sure `SENDER_EMAIL` uses authenticated domain

**Server won't start?**
1. Run `npm install` to install dependencies
2. Check `.env` file exists and has `SENDGRID_API_KEY`
3. Make sure port 3000 is available

**Database errors?**
1. Delete `deadman.db` file
2. Restart server (will recreate database)

---

**Built by ringmast4r**

**Version:** 2.0 (Server-Powered Edition)

---

<a id="-quick-links"></a>
## `> quick_links`

- [GitHub Repository](https://github.com/Ringmast4r/DEAD-MANS-TRIGGER)
- [Report Issues](https://github.com/Ringmast4r/DEAD-MANS-TRIGGER/issues)
- [SendGrid Signup](https://signup.sendgrid.com/)
- [Domain Authentication Guide](https://app.sendgrid.com/settings/sender_auth)

---

<div align="center">

<img width="100%" alt="DEAD MANS TRIGGER footer" src="https://capsule-render.vercel.app/api?type=waving&color=0:627B29,100:000000&height=120&section=footer&text=RINGMAST4R%20%2F%2F%20DEMO&fontSize=18&fontColor=ffffff&fontAlignY=65"/>

</div>
