# Setting Production Branch in Vercel

## Current Status

✅ **Repository Connected**: `Mabspro/EDC`  
✅ **Deployment Source**: Shows `main` branch in production deployment  
⚠️ **Production Branch Setting**: May need to be explicitly set

## How to Set/Verify Production Branch

### Option 1: In Vercel Dashboard (Recommended)

1. Go to your Vercel project dashboard
2. Click **Settings** (gear icon or from left sidebar)
3. Click **Git** in the left sidebar
4. Look for **"Production Branch"** section
5. If it's not set or shows a different branch:
   - Click **Edit** or the dropdown
   - Select **`main`** from the list
   - Save the changes

### Option 2: Check General Settings

1. Go to **Settings** → **General**
2. Scroll down to **"Git"** section
3. Look for **"Production Branch"** field
4. Ensure it's set to **`main`**

### Option 3: During Project Creation

If you're creating a new project:
- When importing from GitHub, you'll see a branch selector
- Make sure **`main`** is selected as the production branch

## Deployment Hooks (Optional)

**Deployment Hooks are NOT required** for automatic deployments. They're only needed if you want to:
- Trigger deployments manually via API
- Integrate with external services
- Create custom deployment workflows

### Automatic Deployments Work Without Hooks

Vercel automatically deploys when you:
- Push to `main` branch → Production deployment
- Push to other branches → Preview deployment
- Open a Pull Request → Preview deployment

**You don't need deployment hooks for this to work!**

## Verification Checklist

- [ ] Repository connected: `Mabspro/EDC` ✅
- [ ] Production deployment shows source: `main` ✅
- [ ] Settings → Git → Production Branch = `main` (verify this)
- [ ] Latest commit deployed: `24342cf` ✅

## If Production Branch Setting is Missing

If you can't find the "Production Branch" setting:

1. **It might be auto-detected** - Vercel often uses the default branch from GitHub
2. **Check GitHub default branch**:
   - Go to your GitHub repo: `Mabspro/EDC`
   - Go to **Settings** → **Branches**
   - Check what the default branch is (should be `main`)

3. **Force a redeploy**:
   - In Vercel dashboard, go to **Deployments**
   - Click the three dots (⋯) on latest deployment
   - Select **Redeploy**
   - This will use the current branch settings

## Current Deployment Info

From your dashboard:
- **Status**: Ready ✅
- **Source Branch**: `main` ✅
- **Commit**: `24342cf` ✅
- **URL**: `edc-5a8gheres-mabvuto-kaelas-projects.vercel.app`
- **Custom Domain**: `edc-dusky.vercel.app`

## The 404 Issue

The deployment is working, but showing 404. This is likely because:
1. Vercel needs to know to serve `index.html` from root
2. We removed `vercel.json` for auto-detection
3. May need to check Build & Deployment settings

**Next Step**: Check **Settings** → **Build and Deployment** to ensure:
- Framework Preset: "Other" or blank
- Build Command: **EMPTY** (important!)
- Output Directory: **EMPTY**
- Root Directory: `./` (default)

## Summary

- ✅ Repository is connected correctly
- ✅ Deployments are coming from `main` branch
- ⚠️ Verify Production Branch setting in Settings → Git
- ⚠️ Deployment hooks are optional (not needed)
- ⚠️ Fix 404 by checking Build & Deployment settings

