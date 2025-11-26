# Vercel Deployment Guide - Dine In Style

## 🚀 Quick Deploy to Vercel

### Option 1: Deploy via Vercel Dashboard (Recommended)

1. **Download your project files**
   - Download all files from this project to a folder on your computer

2. **Create a GitHub repository (recommended)**
   - Go to [github.com](https://github.com) and create a new repository
   - Upload all your project files to this repository
   - OR use GitHub Desktop to push your local folder

3. **Deploy to Vercel**
   - Go to [vercel.com](https://vercel.com)
   - Sign up or log in (you can use your GitHub account)
   - Click "Add New..." → "Project"
   - Import your GitHub repository
   - Vercel will auto-detect the settings (Framework: Vite)
   - Click "Deploy"
   - Wait 1-2 minutes for the build to complete
   - Your site will be live! 🎉

### Option 2: Deploy via Vercel CLI

1. **Install Vercel CLI**
   ```bash
   npm install -g vercel
   ```

2. **Navigate to your project folder**
   ```bash
   cd path/to/dine-in-style
   ```

3. **Deploy**
   ```bash
   vercel
   ```
   - Follow the prompts
   - First time: Login with your Vercel account
   - Confirm project settings
   - Your site will be deployed automatically

4. **Deploy to Production**
   ```bash
   vercel --prod
   ```

### Option 3: Deploy via Drag & Drop

1. Go to [vercel.com](https://vercel.com)
2. Sign up or log in
3. Drag and drop your project folder directly onto the Vercel dashboard
4. Wait for deployment to complete

## 📋 Pre-Deployment Checklist

✅ All files are present:
- `index.html`
- `main.tsx`
- `App.tsx`
- `package.json`
- `vite.config.ts`
- `vercel.json` (new!)
- `tsconfig.json`
- All component files
- All data files
- All style files

✅ Dependencies are correctly listed in `package.json`

✅ Build command is set to `npm run build`

✅ Output directory is set to `dist`

## 🔧 Vercel Configuration

Your project includes a `vercel.json` file with the following settings:

```json
{
  "buildCommand": "npm run build",
  "outputDirectory": "dist",
  "framework": "vite",
  "rewrites": [
    {
      "source": "/(.*)",
      "destination": "/index.html"
    }
  ]
}
```

This ensures:
- Vite builds your project correctly
- All routes work properly (SPA routing)
- Assets are served from the correct directory

## 📱 After Deployment

1. **Get your live URL**
   - Vercel will provide a URL like: `https://your-project-name.vercel.app`
   - You can add a custom domain in the Vercel dashboard

2. **Test your site**
   - Browse products
   - Test the cart functionality
   - Try the WhatsApp integration with your business number (+44730886291)
   - Test on mobile devices

3. **Share your catalogue**
   - Share the Vercel URL with your customers
   - Add it to your WhatsApp Business profile
   - Use it in your marketing materials

## 🔄 Making Updates

After deployment, any changes you push to your GitHub repository will automatically trigger a new deployment on Vercel.

### Update Process:
1. Make changes to your code locally
2. Commit and push to GitHub
3. Vercel automatically rebuilds and deploys
4. Your site is updated in 1-2 minutes

## 💡 Custom Domain (Optional)

To use your own domain (e.g., dineinstyle.com):

1. Go to your project in Vercel dashboard
2. Click "Settings" → "Domains"
3. Add your custom domain
4. Follow the DNS configuration instructions
5. Wait for DNS propagation (5 minutes to 48 hours)

## 🐛 Troubleshooting

**Build fails?**
- Check the build logs in Vercel dashboard
- Ensure all dependencies are in `package.json`
- Try building locally with `npm run build`

**404 errors?**
- The `vercel.json` rewrites should handle this
- Check that the file exists in your project

**WhatsApp not working?**
- Verify your WhatsApp Business number is correct
- Test the WhatsApp URL format in a browser

## 📞 Support

- Vercel Docs: [vercel.com/docs](https://vercel.com/docs)
- Vercel Support: Available in the dashboard

## ✅ You're Ready!

Your Dine In Style catalogue is now ready to deploy to Vercel. Choose your preferred deployment method above and your professional product catalogue will be live in minutes!
