# Deployment Guide

This guide explains how to deploy the AI Chat Website to various hosting platforms.

## 🚀 Quick Deployment Options

### 1. **Vercel** (Recommended)
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel

# For production
vercel --prod
```

**Environment Variables on Vercel:**
- Go to Project Settings → Environment Variables
- Add:
  - `VITE_API_BASE_URL`
  - `VITE_API_AUTH_TOKEN`
  - `VITE_API_MODEL`

### 2. **Netlify**
```bash
# Install Netlify CLI
npm i -g netlify-cli

# Deploy
netlify deploy

# For production
netlify deploy --prod
```

**Netlify Configuration:**
- Build command: `npm run build`
- Publish directory: `dist`
- Environment variables in Netlify UI

### 3. **GitHub Pages**
```bash
# Build the project
npm run build

# Deploy to gh-pages branch
npm run deploy
```

Add to `package.json` scripts:
```json
"deploy": "gh-pages -d dist"
```

Install gh-pages:
```bash
npm install --save-dev gh-pages
```

### 4. **Firebase Hosting**
```bash
# Install Firebase CLI
npm i -g firebase-tools

# Initialize Firebase
firebase init

# Deploy
firebase deploy
```

Select: Hosting → Configure as SPA → Build directory: `dist`

## 📦 Build Configuration

### Production Build
```bash
npm run build
```

Output files in `dist/` folder:
- `index.html`
- `assets/` (JavaScript, CSS, images)
- Static assets

### Development Server
```bash
npm run dev
```
Runs on `http://localhost:3000`

### Preview Build
```bash
npm run preview
```
Preview production build locally

## 🔧 Environment Configuration

### Development (.env.development)
```
VITE_API_BASE_URL=https://dattio.my.id
VITE_API_AUTH_TOKEN=sk-qwen-50c24d57ee4027cb8dad59535d4178270c046cd732a088e8
VITE_API_MODEL=deepseek-v4-pro
VITE_DEFAULT_THEME=light
```

### Production (.env.production)
```
VITE_API_BASE_URL=https://dattio.my.id
VITE_API_AUTH_TOKEN=${API_TOKEN}
VITE_API_MODEL=deepseek-v4-pro
VITE_DEFAULT_THEME=auto
```

## 🐳 Docker Deployment

### Dockerfile
```dockerfile
FROM node:18-alpine as builder
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=builder /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

### docker-compose.yml
```yaml
version: '3.8'
services:
  ai-chat:
    build: .
    ports:
      - "3000:80"
    environment:
      - VITE_API_BASE_URL=https://dattio.my.id
      - VITE_API_AUTH_TOKEN=${API_TOKEN}
    restart: unless-stopped
```

### Build and Run
```bash
docker build -t ai-chat-website .
docker run -p 3000:80 ai-chat-website
```

## ☁️ Cloud Platform Deployment

### AWS S3 + CloudFront
1. Build project: `npm run build`
2. Upload to S3 bucket
3. Configure CloudFront distribution
4. Set up SSL certificate
5. Configure environment variables

### Azure Static Web Apps
1. Push to GitHub repository
2. Create Static Web App in Azure Portal
3. Configure build settings:
   - App location: `/`
   - Api location: ``
   - Output location: `dist`
4. Add environment variables

### Google Cloud Run
1. Create Dockerfile
2. Build container image
3. Deploy to Cloud Run
4. Configure environment variables

## 🔐 Security Considerations

### API Tokens
- Never commit API tokens to version control
- Use environment variables
- Rotate tokens regularly
- Use different tokens for development/production

### HTTPS
- Always deploy with HTTPS enabled
- Configure SSL certificates
- Use HSTS headers

### CORS Configuration
Ensure your API endpoint allows your domain:
```javascript
Access-Control-Allow-Origin: https://your-domain.com
Access-Control-Allow-Headers: Authorization, Content-Type
Access-Control-Allow-Methods: POST, OPTIONS
```

## 📊 Monitoring

### Performance Monitoring
- Google Analytics
- Vercel Analytics
- Sentry for error tracking

### Logging
- Console logs in development
- Structured logging in production
- Error tracking services

### Uptime Monitoring
- UptimeRobot
- StatusCake
- Pingdom

## 🔄 Continuous Deployment

### GitHub Actions
```yaml
name: Deploy to Vercel
on:
  push:
    branches: [main]
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
      - run: npm ci
      - run: npm run build
      - run: npx vercel --prod --token=${{ secrets.VERCEL_TOKEN }}
```

## 🚨 Troubleshooting

### Common Issues

1. **API Connection Failed**
   - Check API token validity
   - Verify CORS settings
   - Check network connectivity

2. **Build Errors**
   - Clear node_modules: `rm -rf node_modules`
   - Reinstall: `npm ci`
   - Check Node.js version

3. **Deployment Issues**
   - Check environment variables
   - Verify build output
   - Check hosting platform logs

### Support
- Check browser console for errors
- Review hosting platform logs
- Test API connectivity
- Verify environment variables

## 📈 Optimization

### Performance Optimization
- Minify JavaScript and CSS
- Optimize images
- Enable compression
- Use CDN for assets

### SEO Optimization
- Meta tags in index.html
- Structured data
- Sitemap generation
- SEO-friendly URLs

## 🔄 Update Process

### Update Application
1. Pull latest changes
2. Update dependencies: `npm update`
3. Test locally
4. Deploy to staging
5. Deploy to production

### Rollback Process
1. Revert to previous version
2. Clear CDN cache
3. Update environment variables if needed

---

**Note:** Always test deployment in staging environment before production deployment.