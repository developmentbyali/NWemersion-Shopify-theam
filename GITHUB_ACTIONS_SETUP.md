# GitHub Actions Setup for Shopify Theme Deployment

This project uses GitHub Actions to automatically deploy theme changes to Shopify. Here's how to set it up:

## 🔐 Required GitHub Secrets

You need to add these secrets to your GitHub repository:

### 1. Go to Repository Settings
1. Navigate to: `https://github.com/developmentbyali/NWemersion-Shopify-theam/settings/secrets/actions`
2. Click **"New repository secret"**

### 2. Add These Secrets:

#### `SHOPIFY_STORE`
- **Value:** `storetostorecli`
- **Description:** Your Shopify store handle (without .myshopify.com)

#### `SHOPIFY_CLI_TOKEN`
- **How to get:**
  1. Run: `shopify auth token`
  2. Copy the token that appears
- **Description:** Authentication token for Shopify CLI

#### `SHOPIFY_LIVE_THEME_ID`
- **How to get:**
  1. Run: `shopify theme list --store storetostorecli`
  2. Find your live theme ID (usually marked as "live")
- **Description:** ID of your live/published theme

#### `SHOPIFY_DEV_THEME_ID`
- **How to get:**
  1. Run: `shopify theme list --store storetostorecli`
  2. Find your development theme ID, or
  3. Create a new one: `shopify theme init development-theme`
- **Description:** ID of your development theme for testing

## 🚀 How It Works

### Automatic Deployment:
- **Push to `main`** → Deploys to **Live Theme**
- **Create Pull Request** → Creates/updates **Development Theme**
- **Merge PR** → Deploys to **Live Theme**

### Real-time Collaboration:
1. **Developer A** creates a feature branch
2. **Developer A** pushes changes → GitHub Actions creates development theme
3. **Developer B** can see changes instantly via preview URL
4. **Both developers** can review and test before merging

### Workflow Examples:

**Feature Development:**
```bash
# Create feature branch
git checkout -b feature/new-header

# Make changes...
git add .
git commit -m "Update header design"

# Push to GitHub
git push origin feature/new-header
```
→ **Result:** GitHub Actions creates development theme with your changes

**Go Live:**
```bash
# Create Pull Request on GitHub
# Review changes via development theme preview
# Merge PR → Automatically deploys to live theme
```

## 📱 Preview URLs

After each deployment, you'll get:
- **Development:** `https://storetostorecli.myshopify.com/?preview_theme_id=DEV_THEME_ID`
- **Live:** `https://storetostorecli.myshopify.com/`

## 🔧 Getting Your Tokens and IDs

### Get Shopify CLI Token:
```bash
shopify auth token
```

### List Your Themes:
```bash
shopify theme list --store storetostorecli
```

### Create Development Theme:
```bash
shopify theme init development-auto-deploy --store storetostorecli
```

## 🛠️ Manual Commands (if needed)

**Deploy to development:**
```bash
shopify theme push --store storetostorecli --theme DEV_THEME_ID
```

**Deploy to live:**
```bash
shopify theme push --store storetostorecli --live
```

## 📋 Checklist

- [ ] Add all 4 secrets to GitHub repository
- [ ] Test by creating a Pull Request
- [ ] Verify development theme is created automatically
- [ ] Check that preview URL works
- [ ] Test merge to main deploys to live theme

**Once set up, both developers will see real-time updates automatically! 🎉**