# 🎮 EMOTE-WEB Bot - No Login Version

## ✨ Changes Made
- ✅ Login page **REMOVED** - Direct access to dashboard
- ✅ All original features **PRESERVED**
- ✅ Error handling **IMPROVED**
- ✅ File paths **FIXED** for better compatibility

## 🚀 Quick Start

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Run Bot
```bash
python main.py
```

### 3. Access Dashboard
Open browser:
```
http://localhost:30151
```

**That's it!** No login required - direct access! 🎉

---

## 📡 API Endpoints

### Send Emote (GET)
```bash
http://localhost:30151/join?uid1=USER_ID&emote_id=909000063&tc=TEAM_CODE
```

**Parameters:**
- `uid1` to `uid5` - Target user IDs (1-5 users)
- `emote_id` - Emote ID from emotes.json
- `tc` - Team code (room code)

### Send Emote (POST)
```bash
curl -X POST http://localhost:30151/send_emote \
  -H "Content-Type: application/json" \
  -d '{
    "team_code": "ABC123",
    "emote_id": "909000063",
    "uids": ["123456789", "987654321"]
  }'
```

---

## 📂 File Structure
```
EMOTE-WEB-NO-LOGIN/
├── main.py              # Main bot (LOGIN REMOVED)
├── app.py               # Alternative entry
├── xC4.py               # Core functions
├── xHeaders.py          # Header utilities
├── emotes.json          # Emote database (500+)
├── emotes.txt           # Text list
├── requirements.txt     # Dependencies
├── Pb2/                 # Protobuf files
├── static/              # Images & CSS
│   ├── images/         # Emote images
│   ├── icons/          # Social icons
│   └── style.css
└── templates/           # HTML templates
    └── index.html      # Main dashboard
```

---

## 🎯 Features

### ⚡ Ultra Fast Emote Sending
- Send emotes to **5 users** simultaneously
- Processing time: **~1 second**
- Automatic room join/leave

### 🎨 Web Dashboard
- Clean, modern UI
- 500+ emote library with images
- Search & filter emotes
- Team code management
- Real-time status

### 🔧 Robust Error Handling
- Auto-reconnect on timeout
- Graceful error messages
- Absolute file paths

---

## 🛠️ Bot Account Info

**Pre-configured account:**
- UID: `4258501816`
- Status: Active

**To change account:**
Edit `main.py` line 520:
```python
Uid, Pw = 'YOUR_UID', 'YOUR_PASSWORD_HASH'
```

---

## 🎮 Popular Emotes

| Alias | ID | Description |
|-------|-----|-------------|
| `ak` | 909000063 | AK Max |
| `mp40` | 909000075 | MP40 Max |
| `scar` | 909000068 | Scar Max |
| `groza` | 909041005 | Groza Max |
| `heart` | 909000045 | Heart Emote |
| `throne` | 909000014 | Throne |
| `level100` | 909042007 | Level 100 Badge |

**Full list:** Check `emotes.json` (1500+ lines)

---

## ⚙️ Configuration

### Change Port
Edit `main.py` line 551:
```python
app.run(host='0.0.0.0', port=30151)  # Change 30151
```

### Change Server Region
Edit `main.py` line 59:
```python
server2 = "ind"  # Options: ind, br, sg, me
```

---

## 🔐 Security Warning

⚠️ **IMPORTANT**: No authentication - anyone with access can use!

**Recommended Setup:**
1. ✅ Use only on **localhost**
2. ✅ Enable firewall rules
3. ✅ Don't expose to public internet
4. ✅ Add authentication for production

**For production**, add this to `main.py`:
```python
# Simple API key protection
API_KEY = "your-secret-key-here"

@app.before_request
def check_api_key():
    if request.endpoint in ['send_emote', 'join_and_emote_api']:
        if request.args.get('api_key') != API_KEY:
            return jsonify({"error": "Invalid API key"}), 401
```

---

## 🐛 Troubleshooting

### Bot not connecting?
```bash
# Check if account is valid
# Verify internet connection
# Check firewall settings
```

### "Bot not connected" error?
```
Wait 5-10 seconds after starting bot
Bot needs time to establish TCP connections
```

### Emotes not sending?
```
✅ Verify team code is correct
✅ Check target UIDs are valid
✅ Ensure bot is in same region
```

### Port already in use?
```bash
# Kill existing process
lsof -ti:30151 | xargs kill -9

# Or change port in main.py
```

---

## 📊 Performance

- **Startup Time:** 5-10 seconds
- **Emote Speed:** ~1 second for 4 UIDs
- **Memory Usage:** ~100-200 MB
- **CPU Usage:** Low (async I/O)

---

## 🔄 Auto-Restart

Bot automatically restarts every **7 hours** for token refresh.

To disable auto-restart, edit `main.py` line 565:
```python
# Comment out or change timeout
# await asyncio.wait_for(MaiiiinE(), timeout=7*60*60)
await MaiiiinE()  # Run forever without restart
```

---

## 📝 What Changed from Original?

### ❌ Removed:
- Login page (`/login` route)
- Login authentication (`/do_login` route)
- `login_required` decorator
- Password checking logic

### ✅ Kept Everything Else:
- All original functionality
- Web dashboard
- API endpoints
- Emote database
- Static files
- Templates (except login.html not used)

### ✨ Improved:
- Direct access (no login needed)
- Better error handling
- Absolute file paths
- More robust startup

---

## 💡 Tips

1. **Keep browser tab open** - Bot runs in same process
2. **Use bookmarks** - Save frequently used emote combos
3. **Team codes** - Get from game before sending emotes
4. **UIDs** - Can find in player profiles

---

## ⚖️ Legal Notice

**Educational purposes only!**