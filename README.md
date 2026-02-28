# Shopify Theme - Apple-like Design

A custom Shopify theme with Apple-inspired design system and clean, modern aesthetics.

## 🎨 Design Features

- **Apple-inspired color palette**: Dark header/footer with light content areas
- **Clean typography**: Using Inter font family
- **Minimal design**: Focus on content and user experience
- **Responsive layout**: Works across all device sizes

## 🛠️ Development Setup

### Prerequisites

- [Node.js](https://nodejs.org/) (v18+)
- [Shopify CLI](https://shopify.dev/docs/themes/tools/cli)
- Git for version control

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd shopify-theme-apple
   ```

2. **Install Shopify CLI** (if not already installed)
   ```bash
   npm install -g @shopify/cli@latest
   ```

3. **Connect to your Shopify store**
   ```bash
   shopify theme dev --store your-store-name
   ```

### Development Workflow

1. **Start development server**
   ```bash
   shopify theme dev --store your-store-name
   ```

2. **Make changes** to theme files in your local editor

3. **Preview changes** at the provided localhost URL

4. **Commit changes**
   ```bash
   git add .
   git commit -m "Your commit message"
   git push origin main
   ```

## 📁 Theme Structure

```
├── assets/           # CSS, JS, and image files
├── config/          # Theme settings and configuration
├── layout/          # Theme layout templates
├── locales/         # Translation files
├── sections/        # Reusable theme sections
├── snippets/        # Reusable code snippets
├── templates/       # Page templates
└── blocks/          # Theme blocks
```

## 🎯 Key Customizations

- **Apple-style header**: Dark navigation with clean typography
- **Custom color scheme**: Apple's signature grays and blues
- **Centered navigation**: Apple-inspired menu layout
- **Typography**: Clean, readable font stack

## 🚀 Deployment

1. **Push to live theme**
   ```bash
   shopify theme push --store your-store-name --live
   ```

2. **Or create a new theme**
   ```bash
   shopify theme push --store your-store-name --unpublished
   ```

## 👥 Collaboration

This project is set up for team collaboration:

1. Each developer should have Shopify CLI installed
2. Use feature branches for new developments
3. Test changes on development themes before merging
4. Coordinate theme pushes to avoid conflicts

## 📝 Notes

- Theme settings are stored in `config/settings_data.json`
- Main styles are in `assets/base.css`
- Header customizations are at the bottom of `base.css`

## 🐛 Troubleshooting

- **Colors not updating**: Clear browser cache and restart dev server
- **Liquid errors**: Check syntax in template files
- **CLI issues**: Run `shopify logout` and `shopify login` to refresh authentication