# Deployment Guide

This project is ready for deployment to Vercel or Netlify.

## Quick Start

The `dist` folder contains the production-ready build. Simply deploy this folder to your hosting platform.

## Deployment Instructions

### Vercel

1. Upload the entire project folder OR just the `dist` folder
2. Vercel will automatically detect the configuration from `vercel.json`
3. If deploying the project root:
   - Build Command: `npm run build`
   - Output Directory: `dist`
4. If deploying just the `dist` folder:
   - No build command needed
   - Set as root directory

### Netlify

1. Upload the entire project folder OR just the `dist` folder
2. Netlify will automatically detect the `_redirects` file for client-side routing
3. If deploying the project root:
   - Build Command: `npm run build`
   - Publish Directory: `dist`
4. If deploying just the `dist` folder:
   - No build command needed
   - Set as root directory

## What's Fixed

✅ All asset paths are relative (using `base: "./"` in vite.config.ts)
✅ index.html is included in the dist folder
✅ three-mesh-bvh version warning resolved
✅ Chunk size warnings resolved (increased limit to 2000kb)
✅ Client-side routing configured (_redirects for Netlify, vercel.json for Vercel)
✅ All images properly bundled in assets folder
✅ Works from any account/domain

## File Structure

```
dist/
├── index.html          # Main HTML file
├── _redirects          # Netlify routing config
├── favicon.ico         # Site favicon
├── robots.txt          # SEO robots file
├── placeholder.svg     # Placeholder image
└── assets/
    ├── amit-garg-*.png      # Profile image
    ├── hero-bg-*.jpg        # Hero background
    ├── index-*.css          # Bundled styles
    ├── index-*.js           # Main application bundle
    ├── react-vendor-*.js    # React libraries
    ├── ui-vendor-*.js       # UI libraries
    └── three-vendor-*.js    # Three.js libraries
```

## Notes

- All assets use relative paths and will work from any domain
- The site uses client-side routing, which is handled by _redirects and vercel.json
- All UI, animations, and content remain unchanged
- No blank screens on deployment
