# 📗 PANDUAN DEPLOY GITHUB PAGES (BAHAGIAN 2)

## ⏱️ Masa: 15-20 minit

## ⚠️ PREREQUISITE:
- Apps Script MESTI dah deploy (Bahagian 1)
- Dah ada Apps Script URL
- Ada GitHub account

---

## STEP 1: Generate Icons

### A) Buka Icon Generator

1. Pergi ke folder: `3-TOOLS/`
2. Double-click `icon-generator.html`
3. Akan buka dalam browser

### B) Generate Icons

**Option 1 - Upload Logo:**
1. Click "📤 Upload Logo"
2. Choose logo sekolah (PNG/JPG)
3. Wait for preview

**Option 2 - Default Icon:**
1. Click "✨ Generate Default Icon"
2. Auto generate dengan icon 🔬

### C) Download Icons

1. Click "⬇️ Download icon-192.png"
2. Click "⬇️ Download icon-512.png"
3. Save both files

### D) Copy Icons

1. Copy `icon-192.png` to: `2-GITHUB-PAGES/icons/`
2. Copy `icon-512.png` to: `2-GITHUB-PAGES/icons/`

✅ **Icons ready!**

---

## STEP 2: Configure API URL

**PENTING! STEP NI WAJIB!**

### A) Buka index.html

1. Pergi ke: `2-GITHUB-PAGES/`
2. Right-click `index.html`
3. Open with: **Notepad** atau **Text Editor**

### B) Find Configuration Line

Press Ctrl+F and search for:
```
PASTE_YOUR_APPS_SCRIPT_URL_HERE
```

You'll find this around line 656:
```javascript
const APPS_SCRIPT_URL = 'PASTE_YOUR_APPS_SCRIPT_URL_HERE';
```

### C) Replace with Your URL

**BEFORE:**
```javascript
const APPS_SCRIPT_URL = 'PASTE_YOUR_APPS_SCRIPT_URL_HERE';
```

**AFTER:**
```javascript
const APPS_SCRIPT_URL = 'https://script.google.com/macros/s/AKfycbxxxxx/exec';
```

⚠️ **MUST include '/exec' at the end!**

### D) Save File

1. Ctrl+S to save
2. Close editor

✅ **Configuration complete!**

---

## STEP 3: Create GitHub Repository

### A) Go to GitHub

1. Login to https://github.com
2. Click **"+"** (top right)
3. Select **"New repository"**

![New Repo](https://i.imgur.com/placeholder-newrepo.png)

### B) Repository Settings

Fill in:
- **Repository name:** `smktc-tempahan` (or any name)
- **Description:** "Sistem Tempahan Eksperimen SMKTC"
- **Public** (must be public for GitHub Pages)
- ☑️ Initialize with README (optional)

![Repo Settings](https://i.imgur.com/placeholder-reposettings.png)

Click **"Create repository"**

---

## STEP 4: Upload Files

### A) Upload via Web (Easiest)

1. In your repo, click **"Add file"** → **"Upload files"**

2. Drag & drop these files dari `2-GITHUB-PAGES/`:
   ```
   index.html
   manifest.json
   service-worker.js
   ```

3. Drag the **icons** folder too
   (Will create icons/ with icon-192.png and icon-512.png)

![Upload Files](https://i.imgur.com/placeholder-upload.png)

4. Scroll down
5. Commit message: "Initial deployment"
6. Click **"Commit changes"**

**File structure patut jadi:**
```
smktc-tempahan/
├── index.html
├── manifest.json
├── service-worker.js
└── icons/
    ├── icon-192.png
    └── icon-512.png
```

---

## STEP 5: Enable GitHub Pages

### A) Go to Settings

1. Click **"Settings"** tab
2. Scroll down, click **"Pages"** (left sidebar)

![Pages Settings](https://i.imgur.com/placeholder-pages.png)

### B) Configure Source

1. **Source:** Deploy from a branch
2. **Branch:** main (or master)
3. **Folder:** / (root)
4. Click **"Save"**

![Configure Pages](https://i.imgur.com/placeholder-pagesconfig.png)

### C) Wait for Deployment

1. Refresh page after 1-2 minutes
2. Will see green box:
   ```
   Your site is live at https://[username].github.io/smktc-tempahan/
   ```

![Live Site](https://i.imgur.com/placeholder-live.png)

3. **COPY this URL!**

---

## STEP 6: Test PWA

### A) Open in Browser

1. Open GitHub Pages URL
2. Should see system loading
3. Form should appear

![PWA Loading](https://i.imgur.com/placeholder-pwaload.png)

### B) Test Form Submission

1. Fill in form
2. Click "Hantar Tempahan"
3. Should show success message
4. Check Google Sheets - data should appear

### C) Test PWA Install (Mobile)

**Android (Chrome):**
1. Open site in Chrome
2. Bottom popup: "Add to Home Screen"
3. Click "Add"
4. Icon appears on home screen
5. Open - fullscreen mode!

**iPhone (Safari):**
1. Open site in Safari
2. Click Share button
3. Scroll down → "Add to Home Screen"
4. Click "Add"
5. Icon appears
6. Open - fullscreen mode!

![Install PWA](https://i.imgur.com/placeholder-install.png)

---

## ✅ DONE - GITHUB PAGES DEPLOYED!

**Your PWA URLs:**

**Main Site:**
```
https://[username].github.io/smktc-tempahan/
```

**This URL:**
- ✅ Can install as app
- ✅ Works offline (cached)
- ✅ Fullscreen mode
- ✅ Professional look

---

## 🎯 SHARE WITH USERS:

**Option 1:** Apps Script URL (works immediately)
```
https://script.google.com/macros/s/AKfycbxxxxx/exec
```

**Option 2:** GitHub Pages URL (PWA features)
```
https://[username].github.io/smktc-tempahan/
```

**Both work! Same backend!**

---

## 🔄 UPDATE SYSTEM:

### Update Frontend (GitHub Pages):

1. Edit files locally
2. Go to GitHub repo
3. Click file to edit
4. Click ✏️ edit icon
5. Make changes
6. Commit changes
7. Wait 1-2 min for auto-deploy

### Update Backend (Apps Script):

1. Edit in Apps Script editor
2. Click Deploy → Manage deployments
3. Click ✏️ edit
4. New version
5. Deploy

**No need to update GitHub!** API URL stays same.

---

## 🎨 CUSTOMIZATION (Optional):

### Change Colors:

Edit `index.html` around line 30-50:
```css
:root{
  --primary:#002D5C;     /* Change this */
  --accent:#0078D4;      /* And this */
}
```

### Change School Name:

Search and replace "SMK Taman Connaught" with your school name.

### Custom Domain (Advanced):

1. Buy domain (e.g., tempahan.smktc.edu.my)
2. GitHub Settings → Pages → Custom domain
3. Add CNAME record in domain DNS
4. Wait for verification

---

## 📝 TROUBLESHOOTING:

| Issue | Solution |
|-------|----------|
| Form not submitting | Check APPS_SCRIPT_URL correct? |
| "Failed to fetch" error | Check Apps Script deployed & URL correct |
| Icons not showing | Check files in icons/ folder |
| PWA not installing | Must use HTTPS (GitHub Pages auto HTTPS) |
| Changes not showing | Clear browser cache, wait 2-3 min |

**More help:** Check `4-DOCS/TROUBLESHOOTING.md`

---

## 🎉 CONGRATULATIONS!

You now have:
- ✅ Working booking system
- ✅ Installable PWA
- ✅ Professional interface
- ✅ Free hosting
- ✅ Easy updates

**Total Cost: RM 0** 💰

**Created:** 2026-04-25  
**Version:** 1.0
