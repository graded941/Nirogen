# NIROGEN - Vercel Deployment Instructions

## Overview
This document provides step-by-step instructions for deploying the NIROGEN web application to Vercel with the simplified authentication system.

## Prerequisites
- Vercel account
- GitHub account
- Database provider (MySQL/TiDB)

## Environment Variables Required

### Required Variables
- `DATABASE_URL` - MySQL/TiDB connection string
- `JWT_SECRET` - Secret for session management (generate a random string)

### Optional Variables
- `NODE_ENV` - Set to "production" (automatically set by Vercel)

## Deployment Steps

### 1. Prepare Your Repository
1. Ensure all changes are committed to Git
2. Push your changes to GitHub

### 2. Create Vercel Project
1. Go to [vercel.com](https://vercel.com) and sign in
2. Click "New Project"
3. Import your GitHub repository
4. Vercel will automatically detect the framework and build settings

### 3. Configure Environment Variables
1. In the Vercel project dashboard, go to "Settings" → "Environment Variables"
2. Add the following variables:
   - `DATABASE_URL`: Your MySQL/TiDB connection string
   - `JWT_SECRET`: Generate a secure random string (use: `openssl rand -base64 32`)

### 4. Database Setup
1. Set up a MySQL/TiDB database (recommended: TiDB Serverless for free tier)
2. Get the connection string
3. Add it to `DATABASE_URL` environment variable

### 5. Deploy
1. Click "Deploy" to trigger the first deployment
2. Wait for the build to complete
3. Your app will be available at a `.vercel.app` subdomain

## Post-Deployment Setup

### 1. Initialize Admin Credentials
The application will automatically create default admin credentials:
- Username: `admin`
- Password: `Nirogenic.1`

**Important**: Change the default password immediately after first login.

### 2. Access Admin Dashboard
1. Navigate to `https://your-app.vercel.app/admin/login`
2. Login with default credentials
3. Change password immediately
4. Add your projects, testimonials, and services

## Database Schema
The application will automatically create the necessary tables on first run:
- `adminCredentials` - Admin login credentials
- `projects` - Portfolio projects
- `testimonials` - Client testimonials
- `services` - Services offered
- `contactSubmissions` - Contact form submissions

## Custom Domain (Optional)
1. In Vercel dashboard, go to "Domains"
2. Add your custom domain
3. Configure DNS records as instructed by Vercel
4. Wait for SSL certificate to be issued

## Monitoring
- Vercel provides built-in analytics and monitoring
- Check the "Logs" tab for any errors
- Monitor build status in the "Deployments" tab

## Troubleshooting

### Build Errors
- Check that all dependencies are installed with `--legacy-peer-deps`
- Verify environment variables are correctly set
- Check the build logs for specific error messages

### Database Connection Issues
- Verify `DATABASE_URL` is correct
- Ensure database is accessible from Vercel's network
- Check database credentials and permissions

### Authentication Issues
- Clear browser cookies if experiencing login issues
- Verify `JWT_SECRET` is set
- Check admin credentials in database

## Security Notes
- Always use strong, unique passwords
- Regularly update dependencies
- Monitor for suspicious activity
- Use HTTPS (automatically provided by Vercel)

## Performance Optimization
The application includes several optimizations:
- Code splitting and lazy loading
- Optimized asset delivery
- Efficient database queries
- Caching headers for static assets

## Support
For issues related to:
- **Vercel deployment**: Contact Vercel support
- **Application bugs**: Check GitHub issues or create a new one
- **Database issues**: Contact your database provider

## Next Steps
1. Deploy to production
2. Set up custom domain
3. Configure monitoring
4. Add initial content through admin dashboard
5. Test all functionality
6. Monitor performance and usage
