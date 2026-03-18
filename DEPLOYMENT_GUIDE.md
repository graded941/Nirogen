# NIROGEN Deployment Guide

## Overview

This guide covers the optimization, configuration, and deployment of the NIROGEN brand website to Vercel with GitHub integration.

## Prerequisites

- Node.js 20.x or higher
- pnpm package manager
- GitHub account with repository access
- Vercel account

## Environment Variables

The following environment variables are required for production deployment. They are automatically injected by the Manus platform:

### Database & Auth
- `DATABASE_URL` - MySQL/TiDB connection string
- `JWT_SECRET` - Session cookie signing secret

### OAuth (Manus)
- `VITE_APP_ID` - Manus OAuth application ID
- `OAUTH_SERVER_URL` - Manus OAuth backend base URL
- `VITE_OAUTH_PORTAL_URL` - Manus login portal URL (frontend)

### Owner Information
- `OWNER_OPEN_ID` - Owner's Manus OpenID
- `OWNER_NAME` - Owner's name

### APIs & Services
- `BUILT_IN_FORGE_API_URL` - Manus built-in APIs base URL
- `BUILT_IN_FORGE_API_KEY` - Bearer token for server-side API access
- `VITE_FRONTEND_FORGE_API_KEY` - Bearer token for frontend API access
- `VITE_FRONTEND_FORGE_API_URL` - Frontend API URL

### Analytics
- `VITE_ANALYTICS_ENDPOINT` - Umami analytics endpoint
- `VITE_ANALYTICS_WEBSITE_ID` - Umami website ID

## Local Development

### Setup
```bash
# Install dependencies
pnpm install

# Set up database
pnpm db:push

# Start development server
pnpm dev
```

The dev server will start on http://localhost:3000

### Building Locally
```bash
# Type check
pnpm check

# Build production bundle
pnpm build

# Start production server
pnpm start
```

## Deployment to Vercel

### Step 1: Connect GitHub Repository

1. Push your code to GitHub main branch
2. Go to [Vercel Dashboard](https://vercel.com/dashboard)
3. Click "Add New Project"
4. Select your GitHub repository
5. Vercel will auto-detect the framework (Vite)

### Step 2: Configure Environment Variables

In Vercel project settings, add all required environment variables listed above.

### Step 3: Configure Build Settings

The `vercel.json` file is already configured with:
- Build command: `pnpm build`
- Dev command: `pnpm dev`
- Install command: `pnpm install --frozen-lockfile`
- Framework: Vite
- Output directory: `dist/public`

### Step 4: Deploy

Vercel will automatically deploy on every push to the main branch.

## Performance Optimizations

### Mobile Responsiveness
- ✓ Mobile-first design approach
- ✓ Responsive typography and spacing
- ✓ Touch-friendly button sizes (min 44x44px)
- ✓ Optimized navigation for small screens
- ✓ Proper viewport meta tag configuration

### Bundle Optimization
- ✓ Code splitting via Vite
- ✓ Lazy loading of routes
- ✓ Tree shaking of unused code
- ✓ CSS optimization with Tailwind
- ✓ Font loading optimization with display=swap

### Image & Asset Optimization
- ✓ CDN URLs for all static assets (via manus-upload-file)
- ✓ No local image storage (prevents deployment timeouts)
- ✓ Proper image formats and compression

### Runtime Optimization
- ✓ Database connection pooling
- ✓ Query optimization with Drizzle ORM
- ✓ API route caching strategies
- ✓ Efficient React rendering with React Query

## Monitoring & Debugging

### Vercel Analytics
- Monitor deployment status in Vercel dashboard
- Check build logs for errors
- Review function execution times

### Application Logs
- Server logs available in Vercel function logs
- Client logs can be monitored via Umami analytics
- Error tracking via console and network requests

## Troubleshooting

### Build Failures
1. Check environment variables are set correctly
2. Verify database connection string
3. Review build logs in Vercel dashboard
4. Ensure all dependencies are installed locally

### Runtime Errors
1. Check database connectivity
2. Verify API endpoints are accessible
3. Review error logs in Vercel function logs
4. Test locally with `pnpm build && pnpm start`

### Performance Issues
1. Check Lighthouse scores in Vercel Analytics
2. Review bundle size with `pnpm build`
3. Monitor database query performance
4. Check network waterfall in browser DevTools

## Security Best Practices

### Implemented
- ✓ HTTPS enforced
- ✓ Secure cookies (httpOnly, secure, sameSite)
- ✓ CSRF protection via session tokens
- ✓ Input validation on all forms
- ✓ SQL injection prevention (Drizzle ORM)
- ✓ XSS protection via React

### Additional Recommendations
- Enable Vercel's DDoS protection
- Set up rate limiting for API routes
- Monitor for suspicious activity
- Keep dependencies updated
- Regular security audits

## Maintenance

### Regular Tasks
- Monitor application performance
- Review error logs weekly
- Update dependencies monthly
- Test all functionality after updates
- Backup database regularly

### Deployment Checklist
- [ ] All environment variables configured
- [ ] Database migrations applied
- [ ] Tests passing locally
- [ ] Build succeeds locally
- [ ] No console errors in production
- [ ] All pages load correctly
- [ ] Forms submit successfully
- [ ] Admin panel accessible
- [ ] Analytics tracking working

## Support

For issues with:
- **Vercel deployment**: Check [Vercel Docs](https://vercel.com/docs)
- **Database**: Review Drizzle ORM documentation
- **React/Vite**: Check framework documentation
- **Manus platform**: Contact support at https://help.manus.im

## Version History

- **v1.0.0** - Initial deployment
  - Full-stack React + Express + tRPC
  - Admin dashboard with content management
  - Mobile-optimized responsive design
  - Vercel deployment ready
