# Deployment Guide

## GitHub Setup

The repository is connected to: https://github.com/Mabspro/EDC.git

### First Time Push

If this is your first push to the repository, run:

```bash
git push -u origin main
```

### Subsequent Pushes

After the initial push, you can use:

```bash
git add .
git commit -m "Your commit message"
git push
```

## Vercel Deployment

### Automatic Deployment via GitHub

1. **Connect Repository to Vercel**
   - Go to [vercel.com](https://vercel.com)
   - Sign in with your GitHub account
   - Click "Add New Project"
   - Import the repository: `Mabspro/EDC`
   - Vercel will automatically detect it's a static site

2. **Configuration**
   - **Framework Preset**: Other (or leave as default)
   - **Root Directory**: `./` (root)
   - **Build Command**: Leave empty (static site, no build needed)
   - **Output Directory**: Leave empty (serves from root)
   - **Install Command**: `npm install` (optional, for consistency)

3. **Environment Variables**
   - None required for this static site

4. **Deploy**
   - Click "Deploy"
   - Vercel will automatically deploy on every push to `main` branch

### Manual Deployment

You can also deploy manually using Vercel CLI:

```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel

# Deploy to production
vercel --prod
```

### Custom Domain

1. In Vercel dashboard, go to your project settings
2. Navigate to "Domains"
3. Add your custom domain (e.g., excellencedataconsulting.com)
4. Follow DNS configuration instructions

## Deployment Checklist

- [x] Repository connected to GitHub
- [x] Vercel configuration file created (`vercel.json`)
- [ ] Push code to GitHub
- [ ] Connect repository to Vercel
- [ ] Verify deployment
- [ ] Set up custom domain (if needed)
- [ ] Update sitemap.xml with production URL
- [ ] Test all pages and functionality

## Post-Deployment

After deployment, update `public/sitemap.xml` with your production domain:

```xml
<loc>https://your-domain.vercel.app/</loc>
```

Or if using custom domain:

```xml
<loc>https://excellencedataconsulting.com/</loc>
```

## Continuous Deployment

Once connected, Vercel will automatically:
- Deploy on every push to `main` branch
- Create preview deployments for pull requests
- Provide deployment URLs for each commit

## Troubleshooting

### Build Errors
- Ensure `package.json` exists (already done)
- Check that all file paths are correct
- Verify images are in `public/images/` directory

### 404 Errors
- Ensure `index.html` is in the root directory
- Check that `vercel.json` routes are configured correctly

### Image Not Loading
- Verify image paths in HTML use `public/images/` prefix
- Check that images are committed to the repository

