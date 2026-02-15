# Vercel Deployment Guide

## Quick Fix for Blank Page Error

The error `supabaseUrl is required` means environment variables are missing in Vercel.

## Step-by-Step Setup

### 1. Add Environment Variables in Vercel

1. Go to your Vercel dashboard: https://vercel.com/dashboard
2. Select your project
3. Go to **Settings** → **Environment Variables**
4. Add these three variables:

| Name | Value | Environment |
|------|-------|-------------|
| `VITE_SUPABASE_PROJECT_ID` | Your Supabase project ID | Production, Preview, Development |
| `VITE_SUPABASE_PUBLISHABLE_KEY` | Your Supabase anon key | Production, Preview, Development |
| `VITE_SUPABASE_URL` | `https://[your-project-id].supabase.co` | Production, Preview, Development |

**⚠️ IMPORTANT:** Select **ALL THREE ENVIRONMENTS** (Production, Preview, Development) for each variable!

### 2. Get Your Supabase Credentials

1. Go to https://supabase.com/dashboard
2. Select your project
3. Go to **Settings** → **API**
4. Copy:
   - **Project URL** → Use as `VITE_SUPABASE_URL`
   - **Project API Key (anon public)** → Use as `VITE_SUPABASE_PUBLISHABLE_KEY`
   - **Project ID** (from URL or settings) → Use as `VITE_SUPABASE_PROJECT_ID`

### 3. Redeploy

After adding environment variables:
1. Go to **Deployments** tab in Vercel
2. Click on the latest deployment
3. Click **⋯** (three dots) → **Redeploy**
4. Wait for deployment to complete

### 4. Verify

Visit your Vercel URL - you should now see the application instead of a blank page!

## Common Issues

**Q: Still seeing blank page after adding env vars?**
- Make sure you selected ALL THREE environments when adding variables
- Verify the values are correct (no extra spaces)
- Try redeploying again

**Q: How do I know if it's working?**
- Open browser console (F12)
- If you see the booking form, it's working!
- If you still see "supabaseUrl is required", variables aren't loaded

## Files Added for Vercel

- ✅ `vercel.json` - SPA routing configuration
- ✅ `.env.example` - Template for required environment variables

## Next Steps

Once deployed successfully:
1. Test the booking form
2. Test the admin dashboard at `/admin/morocco-cmd`
3. Set up a custom domain (optional)
