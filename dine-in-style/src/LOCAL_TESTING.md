# 🧪 Local Testing Guide

## Before You Deploy: Test Your Site Locally

Testing your website on your computer before deploying ensures everything works perfectly!

---

## Prerequisites

✅ Node.js installed (v18 or higher)
✅ All project files in a folder
✅ Terminal/Command Prompt access

---

## Step 1: Open Terminal

### On Mac:
1. Press `Cmd + Space`
2. Type "Terminal"
3. Press Enter

### On Windows:
1. Press `Win + R`
2. Type `cmd`
3. Press Enter

### On Linux:
1. Press `Ctrl + Alt + T`

---

## Step 2: Navigate to Project

```bash
cd path/to/dine-in-style
```

**Examples:**
- Mac: `cd ~/Downloads/dine-in-style`
- Windows: `cd C:\Users\YourName\Downloads\dine-in-style`
- Linux: `cd ~/Downloads/dine-in-style`

**Tip**: You can drag the folder into Terminal (Mac/Linux) to auto-fill the path!

---

## Step 3: Install Dependencies

```bash
npm install
```

**What to expect:**
- Takes 1-3 minutes
- Downloads ~200-300 MB of packages
- Creates a `node_modules` folder
- You'll see lots of text - this is normal!

**Success looks like:**
```
added 500 packages in 45s
```

**Common errors:**
- `npm: command not found` → Install Node.js
- `permission denied` → Use `sudo npm install` (Mac/Linux)
- `network error` → Check your internet connection

---

## Step 4: Start Development Server

```bash
npm run dev
```

**What to expect:**
```
  VITE v6.0.3  ready in 500 ms

  ➜  Local:   http://localhost:5173/
  ➜  Network: use --host to expose
  ➜  press h + enter to show help
```

**Success!** Your server is running ✅

---

## Step 5: Open in Browser

1. Open your web browser (Chrome, Firefox, Safari, Edge)
2. Go to: **http://localhost:5173**
3. You should see your Dine In Style website!

**Can't access?**
- Make sure the dev server is still running
- Try http://127.0.0.1:5173 instead
- Check no other service is using port 5173

---

## Step 6: Test Features

### ✅ Visual Check
- [ ] Header appears when scrolling down
- [ ] Hero section displays properly
- [ ] All products show with images
- [ ] Layout looks good
- [ ] Colors and fonts are correct

### ✅ Functionality Check
- [ ] Category filter works (All, Cutlery, etc.)
- [ ] Click on category buttons
- [ ] Products filter correctly
- [ ] "Add to Order" buttons work
- [ ] Quantity controls (+/-) work
- [ ] Cart button appears (bottom right)
- [ ] Cart shows correct items
- [ ] Remove from cart works
- [ ] "Send via WhatsApp" button works

### ✅ Responsive Check
1. **Desktop View** (default)
   - Resize browser window
   - Layout should adapt

2. **Mobile View**
   - Press F12 (Chrome DevTools)
   - Click device icon (top-left)
   - Select iPhone or Android
   - Test all features on mobile view

3. **Tablet View**
   - In DevTools
   - Select iPad or tablet
   - Check layout

### ✅ WhatsApp Integration
1. Add items to cart
2. Click "Send via WhatsApp"
3. Check the generated message:
   ```
   Hello! I'd like to order the following items:

   1. Product Name (DIS-001) - Quantity: 2
   ...
   ```
4. Verify WhatsApp opens (or browser asks permission)
5. Confirm number is +44730886291

---

## Step 7: Test Performance

### Load Time
- Page should load in < 2 seconds
- Images should load smoothly
- No visible lag when scrolling

### Interactions
- Buttons should respond immediately
- Animations should be smooth
- No freezing or stuttering

---

## Common Issues & Fixes

### Issue: "Cannot find module..."
**Fix:**
```bash
npm install
```

### Issue: Changes not showing
**Fix:**
1. Stop server (Ctrl + C)
2. Restart: `npm run dev`
3. Hard refresh browser (Ctrl + Shift + R)

### Issue: Port already in use
**Fix:**
```bash
# Kill the process using port 5173
# Mac/Linux:
lsof -ti:5173 | xargs kill

# Windows:
netstat -ano | findstr :5173
taskkill /PID <process_id> /F

# Or change port in vite.config.ts:
# server: { port: 3000 }
```

### Issue: Images not loading
**Check:**
- Internet connection (Unsplash images)
- Browser console for errors (F12)
- Image URLs in products.ts

### Issue: TypeScript errors
**Fix:**
```bash
npm run build
```
This will show any TypeScript errors

---

## Step 8: Test Build (Production Mode)

Test how your site will work when deployed:

```bash
npm run build
```

**What to expect:**
- Takes 10-30 seconds
- Creates a `dist` folder
- Shows bundle sizes

**Success looks like:**
```
✓ built in 15s
dist/index.html              0.5 kB
dist/assets/index-abc123.js  150 kB
```

**Then preview the production build:**
```bash
npm run preview
```

Open: http://localhost:4173

This is exactly how your site will work on Vercel!

---

## Step 9: Stop the Server

When you're done testing:

1. Go back to Terminal
2. Press `Ctrl + C`
3. Server stops

---

## Performance Checklist

Before deploying, verify:

- [ ] Page loads in < 2 seconds
- [ ] Images load smoothly
- [ ] No console errors (F12 → Console)
- [ ] All features work
- [ ] Mobile view works perfectly
- [ ] Cart system works correctly
- [ ] WhatsApp integration works
- [ ] Build succeeds (`npm run build`)

---

## Console Commands Reference

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview

# Stop server
Ctrl + C

# Clear cache and reinstall
rm -rf node_modules package-lock.json
npm install
```

---

## Browser DevTools Tips

### Open DevTools:
- **Windows/Linux**: F12 or Ctrl + Shift + I
- **Mac**: Cmd + Option + I

### Useful Tabs:
- **Console**: See errors and logs
- **Network**: Check what's loading
- **Elements**: Inspect HTML/CSS
- **Application**: Check local storage
- **Device Toolbar**: Test mobile view

### Common Checks:
1. **Console**: Should be error-free ✅
2. **Network**: All resources should load (green status)
3. **Responsive**: Test all device sizes

---

## Mobile Testing on Real Devices

### Test on Your Phone:

1. Find your computer's IP:
   ```bash
   # Mac/Linux
   ifconfig | grep inet
   
   # Windows
   ipconfig
   ```

2. Start dev server with host:
   ```bash
   npm run dev -- --host
   ```

3. On your phone's browser:
   - Connect to same WiFi as computer
   - Go to: `http://YOUR_IP:5173`
   - Example: `http://192.168.1.100:5173`

4. Test everything on your actual phone!

---

## What to Look For

### Good Signs ✅
- No console errors
- Images load quickly
- Smooth interactions
- Responsive layout
- WhatsApp opens correctly
- Cart system works
- Build succeeds

### Red Flags ❌
- Console errors (red text in F12 → Console)
- Missing images
- Broken layout
- Slow performance
- Features not working
- Build fails

---

## Ready for Deployment?

If everything works perfectly:
- ✅ All features tested
- ✅ No console errors
- ✅ Mobile responsive
- ✅ Build succeeds
- ✅ Performance good

**You're ready to deploy to Vercel!** 🚀

---

## Testing Checklist Summary

- [ ] Dependencies installed
- [ ] Dev server runs
- [ ] Site opens in browser
- [ ] All visual elements correct
- [ ] Category filter works
- [ ] Cart system works
- [ ] WhatsApp integration works
- [ ] Mobile view tested
- [ ] Production build succeeds
- [ ] No console errors
- [ ] Ready to deploy! 🎉

---

## Next Steps

After successful local testing:

1. **Read**: DEPLOYMENT_READY.md
2. **Choose**: Deployment method
3. **Deploy**: Follow VERCEL_DEPLOYMENT.md
4. **Share**: Your live URL! 🌐

---

**Happy Testing! 🧪**
