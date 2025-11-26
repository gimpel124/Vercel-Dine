# Dine In Style - Product Catalogue

A professional product catalogue website for showcasing cutlery and dining items, integrated with WhatsApp Business for customer enquiries.

## ✨ Features

- 📱 **Fully Responsive** - Works perfectly on mobile, tablet, and desktop
- 🛒 **Smart Cart System** - Add multiple items with quantities before ordering
- 📦 **Item Reference Numbers** - Each product has a unique DIS-XXX code for easy identification
- 💬 **WhatsApp Integration** - Send complete orders directly to WhatsApp Business (+44730886291)
- 🎨 **Smart Scroll Header** - Header appears/disappears based on scroll direction
- 🔍 **Category Filtering** - Filter products by category (All, Cutlery, Dinnerware, Glassware, Serveware)
- ⚡ **Fast & Modern** - Built with React, TypeScript, and Vite
- 🎯 **Touch-Friendly** - Optimized for mobile touch interactions

## 🚀 Quick Start

### For Development

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Run development server:**
   ```bash
   npm run dev
   ```

3. **Open in browser:**
   - Navigate to `http://localhost:5173`

### For Production Build

```bash
npm run build
```

The production-ready files will be in the `dist` folder.

## 📦 Deployment

This project is ready to deploy to **Vercel**. See [VERCEL_DEPLOYMENT.md](VERCEL_DEPLOYMENT.md) for detailed deployment instructions.

### Quick Deploy to Vercel:

1. Push your code to GitHub
2. Go to [vercel.com](https://vercel.com)
3. Import your repository
4. Deploy! ✨

## 🏗️ Project Structure

```
dine-in-style/
├── components/           # React components
│   ├── CategoryFilter.tsx
│   ├── Header.tsx
│   ├── Hero.tsx
│   ├── OrderCart.tsx
│   ├── OrderSummary.tsx
│   ├── ProductCard.tsx
│   └── ui/              # UI components
├── data/
│   └── products.ts      # Product catalogue data
├── styles/
│   └── globals.css      # Global styles
├── App.tsx              # Main application component
├── main.tsx             # Application entry point
├── index.html           # HTML template
├── package.json         # Dependencies
├── vite.config.ts       # Vite configuration
├── vercel.json          # Vercel deployment configuration
└── tsconfig.json        # TypeScript configuration
```

## 🛠️ Tech Stack

- **React 18** - UI library
- **TypeScript** - Type safety
- **Vite** - Build tool
- **Tailwind CSS v4** - Styling
- **Lucide React** - Icons
- **Radix UI** - Accessible components

## 📝 Customization

### Adding Products

Edit `/data/products.ts` to add, remove, or modify products:

```typescript
{
  id: 1,
  name: "Product Name",
  reference: "DIS-001",
  category: "Cutlery",
  price: 29.99,
  image: "image-url",
  description: "Product description"
}
```

### Changing WhatsApp Number

Update the WhatsApp number in:
- `/components/Hero.tsx` - Hero section button
- `/components/OrderSummary.tsx` - Cart WhatsApp integration

Current number: **+44730886291**

### Modifying Branding

- **Colors**: Edit `/styles/globals.css`
- **Logo/Header**: Edit `/components/Header.tsx`
- **Hero Section**: Edit `/components/Hero.tsx`

## 📱 WhatsApp Integration

When customers click "Send via WhatsApp" from the cart, a formatted message is created with:
- All selected items
- Quantities
- Reference numbers
- Total items count

The message is sent directly to your WhatsApp Business number.

## 🌐 Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## 📄 License

Private - © 2025 Dine In Style

## 🤝 Support

For questions about your product catalogue, contact Dine In Style via WhatsApp: +44730886291

---

**Built with ❤️ for Dine In Style**
