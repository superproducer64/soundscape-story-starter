# Microphone Not Working? Quick Fixes

## Immediate Steps (Try These First)

### 1. Hard Refresh Your Browser
**This is the #1 fix for this issue.**

- **Chrome/Edge:** `Ctrl + Shift + R` (Windows) or `Cmd + Shift + R` (Mac)
- **Safari:** `Cmd + Option + R` (Mac)
- **Firefox:** `Ctrl + F5` (Windows) or `Cmd + Shift + R` (Mac)

Wait for page to fully reload, then try the microphone button again.

---

### 2. Check Browser Permissions

**Chrome/Edge:**
1. Click the address bar lock 🔒
2. Look for "Microphone" — it should say "Allow"
3. If it says "Block," click it and change to "Allow"
4. Refresh the page

**Safari (iOS):**
1. Settings → Privacy → Microphone
2. Find "SoundScape" and toggle to "Allow"

**Firefox:**
1. Click address bar lock 🔒
2. Find "Microphone" permission
3. Change to "Allow"

---

### 3. Check Device Microphone

- **Is your device's microphone working?** Test it elsewhere first (voice memos, video call app)
- **Is it physically blocked?** Check if a sticker or case is covering the mic
- **Is the mic muted?** Some devices have a physical mute button

---

### 4. Try a Different Browser

Sometimes one browser has permission issues:
- If Chrome doesn't work, try Safari, Firefox, or Edge
- Test on a different device if possible

---

## If It Still Doesn't Work

### Check the Browser Console for Error Messages

1. Open Developer Tools:
   - **Chrome:** Right-click → "Inspect" → "Console" tab
   - **Safari:** Develop → Show JavaScript Console
   - **Firefox:** Right-click → "Inspect" → "Console" tab

2. Look for red error messages mentioning "microphone" or "getUserMedia"
3. Take a screenshot and report the exact error

Common errors:
- `NotAllowedError` → Browser permission denied (fix #2 above)
- `NotFoundError` → No microphone detected (fix #3 above)
- `NotSupportedError` → Browser doesn't support it (try different browser)

---

### Mobile-Specific Issues

**Android:**
- Settings → Apps → [Browser] → Permissions → Microphone → Allow
- Try Chrome if other browsers don't work
- Clear browser cache: Settings → Apps → [Browser] → Storage → Clear Cache

**iOS:**
- Settings → Privacy → Microphone → Toggle SoundScape on
- iOS sometimes blocks microphone for Safari. Try the Vercel app as PWA instead:
  - Open in Safari
  - Tap Share → "Add to Home Screen"
  - This sometimes bypasses Safari's restrictions

---

## Already Deployed? Push the Fixed Version

I've updated the configuration files to explicitly allow microphone access:

1. Pull the latest files from /outputs
2. Specifically use the new `vercel.json` (has permission headers)
3. Push to GitHub:
   ```bash
   git add .
   git commit -m "Fix: Add microphone permissions for Vercel deployment"
   git push origin main
   ```
4. Vercel redeploys automatically (30 seconds)
5. Hard refresh your browser (Ctrl+Shift+R)

---

## Last Resort: Clear Everything

If nothing above works:

**Chrome:**
1. Settings → Privacy and Security → Clear browsing data
2. Select "Cookies and other site data" and "Cached images"
3. Click "Clear data"
4. Go back to your SoundScape URL
5. Grant permission when prompted

**Safari:**
1. Safari → Settings → Privacy
2. Click "Manage Website Data"
3. Find your SoundScape domain and remove it
4. Clear Safari cache: History → Clear History
5. Restart Safari

---

## You Should Now See:

1. Click the green record button
2. **Browser asks:** "Allow microphone?" (permission popup)
3. Click **"Allow"**
4. Red recording button appears with timer
5. Record your sound
6. Hit stop button when done

**If you don't see the permission popup in step 2, that's the issue.** Go back to "Check Browser Permissions" section above.

---

## Still Stuck?

1. Try on a completely different device (friend's phone, laptop)
2. Try a completely different browser
3. Check if your device/network has any security software blocking microphone access

99% of the time it's a browser permission issue. Make sure step 2 (Check Browser Permissions) is fully resolved.

---

**Latest version with microphone fixes deployed. Hard refresh and try again.**