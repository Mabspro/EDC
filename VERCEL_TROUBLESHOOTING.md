# Vercel Deployment Troubleshooting

## Current Issue: 404 Error

If you're seeing a 404 error after deployment, try these solutions:

### Solution 1: Check Vercel Project Settings

In your Vercel dashboard, go to Project Settings → General:

1. **Framework Preset**: Set to "Other" or leave blank
2. **Root Directory**: `./` (leave as default)
3. **Build Command**: Leave **EMPTY** (no build needed for static site)
4. **Output Directory**: Leave **EMPTY** (serves from root)
5. **Install Command**: `npm install` (optional)

### Solution 2: Remove vercel.json (Auto-Detect)

If the simplified config doesn't work, try removing `vercel.json` entirely:

```bash
git rm vercel.json
git commit -m "Remove vercel.json for auto-detection"
git push origin main
```

Vercel will auto-detect it as a static site.

### Solution 3: Verify File Structure

Ensure your files are in the correct locations:
- `index.html` must be in the root directory ✅
- `src/styles.css` ✅
- `src/script.js` ✅
- `public/images/` ✅

### Solution 4: Check Deployment Logs

1. Go to your Vercel project dashboard
2. Click on the latest deployment
3. Check the "Build Logs" tab
4. Look for any errors or warnings

### Solution 5: Manual Redeploy

1. In Vercel dashboard, go to Deployments
2. Click the three dots (⋯) on the latest deployment
3. Select "Redeploy"

### Solution 6: Alternative vercel.json

If needed, try this minimal configuration:

```json
{
  "version": 2
}
```

Or remove it completely and let Vercel auto-detect.

## Verification Checklist

- [ ] Code is pushed to `main` branch
- [ ] `index.html` exists in root directory
- [ ] Vercel project settings are correct
- [ ] Build logs show no errors
- [ ] Deployment completed successfully

## Common Issues

### Issue: "Cannot find module"
- **Solution**: Make sure `package.json` exists (it does ✅)

### Issue: "Build failed"
- **Solution**: Leave Build Command empty for static sites

### Issue: "404 on all routes"
- **Solution**: Ensure `index.html` is in root, or add rewrite rules

### Issue: "Assets not loading"
- **Solution**: Check that paths in HTML are correct (relative to root)

## Still Having Issues?

1. Check Vercel's deployment logs
2. Verify the repository is correctly connected
3. Try redeploying from the Vercel dashboard
4. Contact Vercel support with deployment ID from error page

