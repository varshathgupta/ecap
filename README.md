# E-CAP NGO Website

> **Employment Career Awareness Program (என்னும் வழிகாட்டி)** - A non-profit organization dedicated to guiding students towards successful careers.

## 👋 Welcome New Developers!

This repository contains the official website for E-CAP NGO. If you're new here, you're in the right place! This guide will help you get started quickly.

### What You Need to Know

- **Main Project**: The website is built with **Next.js 14** (a modern React framework)
- **Work Here**: All development happens in the `ecap-nextjs/` folder
- **Tech Stack**: React, TypeScript, Tailwind CSS, Framer Motion
- **Time to Start**: ~5 minutes to get running locally

## 🎯 Repository Structure

```
ecap/
├── ecap-nextjs/        ← 🚀 WORK HERE! (Modern Next.js website)
├── images/             ← Legacy images (being migrated)
├── old-site-backup/    ← 🗄️ Old website (reference only, don't modify)
├── SKILL.md            ← Design guidelines and brand assets
└── README.md           ← This file
```

## ⚡ Quick Start (5 Minutes)

### Step 1: Navigate to the project folder

```bash
cd ecap-nextjs
```

### Step 2: Install dependencies

```bash
npm install
```

### Step 3: Start development server

```bash
npm run dev
```

### Step 4: Open your browser

Visit **http://localhost:3000** - You should see the E-CAP website running locally! 🎉

📖 **For detailed setup instructions**, see the [ecap-nextjs/README.md](ecap-nextjs/README.md)

## �️ Technology Stack

The E-CAP website uses modern web technologies:

| Technology | Purpose | Why We Use It |
|------------|---------|---------------|
| **Next.js 14** | React Framework | Fast, SEO-friendly, easy to deploy |
| **TypeScript** | Type Safety | Catch errors early, better code quality |
| **Tailwind CSS** | Styling | Rapid development, consistent design |
| **Framer Motion** | Animations | Smooth, professional animations |
| **EmailJS** | Contact Form | Free email service integration |

**No backend needed!** This is a static website that can be deployed anywhere.

## 📂 Project Folders Explained

### ✅ `ecap-nextjs/` - **Active Development** (Work Here!)

This is where all the website code lives. Inside you'll find:

```
ecap-nextjs/
├── src/
│   ├── app/           ← Pages and layouts
│   ├── components/    ← Reusable UI components
│   └── hooks/         ← Custom React hooks
├── public/            ← Images and static files
└── package.json       ← Dependencies and scripts
```

**Full documentation**: See [ecap-nextjs/README.md](ecap-nextjs/README.md)

### 📸 `images/` - Legacy Images

Original images from the old website. These are being migrated to `ecap-nextjs/public/images/`

### 🗄️ `old-site-backup/` - Old Website (Reference Only)

The previous HTML/CSS website. Kept for historical reference.
- ❌ **Do not modify these files**
- ✅ Use as reference if needed
- 🗑️ Can be deleted after migration is complete

## 🧑‍💻 Development Workflow

### Making Changes to the Website

1. **Navigate to the project**
   ```bash
   cd ecap-nextjs
   ```

2. **Start the development server**
   ```bash
   npm run dev
   ```
   The site will be available at http://localhost:3000

3. **Make your changes**
   - Edit files in `src/components/` to modify sections
   - Changes appear instantly (hot reload)
   - Check the browser to see your updates

4. **Test before deploying**
   ```bash
   npm run build    # Create production build
   npm run start    # Test production version
   ```

### Common Development Tasks

| Task | Command | When to Use |
|------|---------|-------------|
| Start dev server | `npm run dev` | Daily development |
| Build for production | `npm run build` | Before deploying |
| Check for errors | `npm run lint` | After making changes |
| Install new package | `npm install package-name` | Adding features |

## 🎨 Making Content Changes

### Update Text Content

Most content is in component files:
- **Hero Section**: [ecap-nextjs/src/components/sections/Hero.tsx](ecap-nextjs/src/components/sections/Hero.tsx)
- **About Section**: [ecap-nextjs/src/components/sections/About.tsx](ecap-nextjs/src/components/sections/About.tsx)
- **Programs**: [ecap-nextjs/src/components/sections/Programs.tsx](ecap-nextjs/src/components/sections/Programs.tsx)
- **Team**: [ecap-nextjs/src/components/sections/Team.tsx](ecap-nextjs/src/components/sections/Team.tsx)
- **Contact**: [ecap-nextjs/src/components/sections/Contact.tsx](ecap-nextjs/src/components/sections/Contact.tsx)

### Add Images

1. Place images in `ecap-nextjs/public/images/`
2. Reference in code: `/images/your-image.jpg`
3. Use Next.js Image component for optimization

### Update Styling

- Global styles: [ecap-nextjs/src/app/globals.css](ecap-nextjs/src/app/globals.css)
- Tailwind config: [ecap-nextjs/tailwind.config.ts](ecap-nextjs/tailwind.config.ts)
- Component styles: Use Tailwind utility classes

## 🚀 Deployment

The website can be deployed to various platforms:

### Option 1: Vercel (Recommended - Free & Easy)
1. Push code to GitHub
2. Go to [vercel.com](https://vercel.com)
3. Import your GitHub repository
4. Add environment variables (EmailJS keys)
5. Click Deploy!

### Option 2: Netlify
Similar to Vercel, drag-and-drop or connect GitHub

### Option 3: Traditional Hosting
Export as static site: `npm run build` then deploy the `out/` folder

## 📚 Learning Resources

### New to Next.js?
- [Next.js Documentation](https://nextjs.org/docs) - Official docs
- [Next.js Learn Course](https://nextjs.org/learn) - Interactive tutorial

### New to React?
- [React Documentation](https://react.dev) - Official React docs
- [React Tutorial](https://react.dev/learn) - Step-by-step guide

### New to Tailwind CSS?
- [Tailwind Documentation](https://tailwindcss.com/docs) - How to use Tailwind
- [Tailwind UI](https://tailwindui.com) - Component examples

## ❓ Frequently Asked Questions

### Q: Do I need to know React?
**A:** Basic knowledge helps, but you can start by editing text and styles in the components. The code is well-organized and commented.

### Q: How do I change colors?
**A:** Edit the `tailwind.config.ts` file. Colors are defined in the `theme.colors` section.

### Q: Contact form isn't working?
**A:** You need to set up EmailJS. See the detailed guide in [ecap-nextjs/README.md](ecap-nextjs/README.md#emailjs-setup)

### Q: Can I preview changes before deploying?
**A:** Yes! Run `npm run dev` to see changes locally at http://localhost:3000

### Q: How do I add a new page?
**A:** Create a new folder in `src/app/` (Next.js uses file-based routing)

## 🆘 Troubleshooting

### Port 3000 already in use
```bash
# Kill the process using port 3000
lsof -ti:3000 | xargs kill -9
# Or use a different port
npm run dev -- -p 3001
```

### Dependencies not installing
```bash
# Clear cache and reinstall
rm -rf node_modules package-lock.json
npm install
```

### Build errors
```bash
# Clear Next.js cache
rm -rf .next
npm run build
```

### Still stuck?
- Check the detailed [ecap-nextjs/README.md](ecap-nextjs/README.md)
- Look for errors in the terminal
- Check browser console (F12) for JavaScript errors

## 📞 Contact & Support

### E-CAP NGO
- **Email**: ecapofficial@outlook.com
- **Phone**: +91 97864 06411
- **Website**: Coming soon!

### For Developers
- Check the [detailed documentation](ecap-nextjs/README.md) in the ecap-nextjs folder
- Look at existing components for examples
- Test changes locally before deploying

## 🤝 Contributing

We welcome contributions! Here's how:

1. **Make changes** in a new branch
2. **Test thoroughly** with `npm run dev` and `npm run build`
3. **Document changes** - update README if needed
4. **Submit for review** before merging to main

### Git Workflow

```bash
# Create a new branch for your changes
git checkout -b feature/your-feature-name

# Make your changes, then commit
git add .
git commit -m "Description of changes"

# Push to GitHub
git push origin feature/your-feature-name
```

## 📝 Project Status

- ✅ Next.js website completed
- ✅ All sections implemented
- ✅ Responsive design complete
- ✅ EmailJS contact form integrated
- 🔄 Image migration in progress
- 📅 Deployment pending

## 🎯 Quick Links

- **Main Documentation**: [ecap-nextjs/README.md](ecap-nextjs/README.md)
- **Design Guidelines**: [SKILL.md](SKILL.md)
- **Next.js Docs**: https://nextjs.org/docs
- **Tailwind CSS**: https://tailwindcss.com/docs

---

**Built with ❤️ for E-CAP - Empowering Students, Building Futures**

மாற்றத்திற்கான விதையாய் நாம் இருப்போம் (Let's be the seeds of change)

> **Ready to start?** → `cd ecap-nextjs && npm install && npm run dev`
