# Deployment Guide for Bobby's Portfolio

## Option 1: Deploy to Netlify (For Full CMS Functionality)

### Step 1: Deploy to Netlify
1. Go to [netlify.com](https://netlify.com) and sign in
2. Click "New site from Git"
3. Connect your GitHub account
4. Select the `bdhir2003/new_website` repository
5. Set build settings:
   - Build command: (leave empty)
   - Publish directory: `/` (root)
6. Click "Deploy site"

### Step 2: Enable Netlify Identity
1. In your Netlify site dashboard, go to "Identity"
2. Click "Enable Identity"
3. Go to "Settings and usage"
4. Under "Registration preferences", select "Invite only" or "Open"
5. Under "External providers", you can enable GitHub, Google, etc.

### Step 3: Enable Git Gateway
1. Still in Identity settings, scroll to "Services"
2. Click "Enable Git Gateway"

### Step 4: Create Admin User
1. Go to "Identity" tab in your Netlify dashboard
2. Click "Invite users"
3. Enter your email address
4. Check your email and accept the invitation
5. Set up your password

### Step 5: Access Admin
- Your admin panel will be available at: `https://your-site-name.netlify.app/admin/`

## Option 2: Use Local Admin (For Local Development)

### For Local Testing:
1. Make sure your local server is running: `python3 -m http.server 8000`
2. Access the local admin at: `http://localhost:8000/admin/local-admin.html`
3. This will let you edit content and copy the JSON to update `data/site.json` manually

## Recommended Workflow:
1. Use the local admin for development and testing
2. Deploy to Netlify for production with full CMS capabilities
3. For quick updates, you can always edit `data/site.json` directly

## Files Structure:
```
/
├── index.html          # Main portfolio site
├── admin/
│   ├── index.html      # Netlify CMS (for production)
│   ├── config.yml      # CMS configuration
│   └── local-admin.html # Local development admin
├── assets/
│   └── css/
│       └── style.css
└── data/
    └── site.json       # Content data
```

## Troubleshooting:
- If admin doesn't work on localhost, use the local-admin.html version
- For Netlify CMS to work, you need the full Netlify hosting + Identity setup
- Make sure your site.json file is properly formatted JSON
