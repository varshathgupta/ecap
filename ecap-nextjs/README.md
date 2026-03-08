# E-CAP NGO Website - Next.js Application

# E-CAP NGO Website - Next.js Application

> **Employment Career Awareness Program (என்னும் வழிகாட்டி)** - Official website for a non-profit organization dedicated to guiding students towards successful careers.

## 🎯 What is This Project?

This is a **modern, single-page website** built for E-CAP NGO using Next.js. It's designed to:
- Showcase E-CAP's mission and programs
- Connect with students and educational institutions  
- Provide an easy way for people to contact the organization
- Work perfectly on all devices (mobile, tablet, desktop)

### Why Next.js?

Next.js is a modern React framework that makes building fast, SEO-friendly websites easy. Benefits:
- ⚡ **Fast**: Optimized for performance
- 🔍 **SEO-friendly**: Search engines can find the content
- 📱 **Responsive**: Works on all screen sizes
- 🚀 **Easy to deploy**: One-click deployment to Vercel
- 💻 **Great developer experience**: Hot reload, TypeScript support

## ✨ Key Features

- ✨ **Modern Design**: Warm, humanitarian aesthetic with earthy tones
- 🎨 **Fully Responsive**: Perfect display on mobile, tablet, and desktop
- ⚡ **High Performance**: Built with Next.js 14 and optimized images
- 🎭 **Smooth Animations**: Professional Framer Motion animations
- 📧 **Contact Form**: Integrated EmailJS (no backend server needed!)
- ♿ **Accessible**: WCAG compliant, keyboard navigation, screen reader friendly
- 🌐 **Bilingual**: English and Tamil language support
- 🎨 **Tailwind CSS**: Modern utility-first styling

## 🚀 Getting Started for Beginners

### What You'll Need

Before starting, make sure you have:
- **Node.js** (version 18 or higher) - [Download here](https://nodejs.org/)
- A **code editor** (VS Code recommended) - [Download here](https://code.visualstudio.com/)
- **Terminal/Command line** - Built into VS Code or use your system terminal
- Basic knowledge of React (helpful but not required to start)

### Installation Steps

#### 1. Navigate to the project directory

```bash
cd ecap-nextjs
```

#### 2. Install dependencies

This downloads all the packages the project needs:

```bash
npm install
```

This command reads `package.json` and installs:
- Next.js (framework)
- React (UI library)
- Tailwind CSS (styling)
- Framer Motion (animations)
- EmailJS (contact form)
- TypeScript (type safety)

**Wait for it to complete** - it may take 1-2 minutes.

#### 3. Set up environment variables (for contact form)

The contact form needs EmailJS to work. You have two options:

**Option A: Skip for now** (form won't work but site will run)
- The website will work fine, contact form just won't send emails

**Option B: Set up EmailJS** (5-10 minutes)
- Follow the [EmailJS Setup Guide](#emailjs-setup-detailed) below
- Required for production deployment

#### 4. Start the development server

```bash
npm run dev
```

You should see output like:
```
  ▲ Next.js 14.1.0
  - Local:        http://localhost:3000
  - Ready in 2.3s
```

#### 5. Open in browser

Visit **http://localhost:3000** in your web browser.

🎉 **You should see the E-CAP website!**

### What Happens with `npm run dev`?

- Starts a local development server
- Watches files for changes
- **Hot reload**: When you save a file, changes appear instantly in the browser
- Shows helpful error messages if something goes wrong

### Making Your First Change

Let's make a simple change to verify everything works:

1. Open `src/components/sections/Hero.tsx` in your code editor
2. Find the heading text (around line 20)
3. Change some text
4. Save the file (Ctrl+S or Cmd+S)
5. Look at your browser - the change appears automatically!

**No need to refresh the page** - Next.js hot reloads for you. 🔥

## 📧 EmailJS Setup (Detailed)

The contact form uses EmailJS to send emails without needing a backend server. Here's how to set it up:

### Step 1: Create EmailJS Account (Free)

1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Click "Sign Up" (it's free!)
3. Verify your email address

### Step 2: Create an Email Service

1. In your EmailJS dashboard, click **"Email Services"**
2. Click **"Add New Service"**
3. Choose your email provider:
   - **Gmail** (most common)
   - **Outlook**
   - **Yahoo**
   - Or any other provider
4. Follow the prompts to connect your email
5. **Copy the Service ID** - you'll need this!

### Step 3: Create an Email Template

1. Click **"Email Templates"**
2. Click **"Create New Template"**
3. In the template editor, use these variables:

```
Subject: New Contact Form Submission from {{from_name}}

From: {{from_name}}
Email: {{from_email}}
Phone: {{phone}}
Organization: {{organization}}

Message:
{{message}}

---
Sent from E-CAP website contact form
```

4. Test the template
5. **Copy the Template ID** - you'll need this!

### Step 4: Get Your Public Key

1. Click your profile/account icon
2. Go to **"Account"** → **"General"**
3. Find **"Public Key"**
4. **Copy the Public Key** - you'll need this!

### Step 5: Create Environment File

Create a file named `.env.local` in the `ecap-nextjs/` folder:

```bash
# In terminal, while in ecap-nextjs/ folder
touch .env.local
```

Or create it manually in your code editor.

### Step 6: Add Your Keys

Open `.env.local` and add your EmailJS credentials:

```env
NEXT_PUBLIC_EMAILJS_SERVICE_ID=service_xxxxxxx
NEXT_PUBLIC_EMAILJS_TEMPLATE_ID=template_xxxxxxx
NEXT_PUBLIC_EMAILJS_PUBLIC_KEY=xxxxxxxxxxxx
```

Replace the `xxxxxxx` with your actual IDs and key from EmailJS.

**Important**: Never commit `.env.local` to Git (it's already in `.gitignore`)!

### Step 7: Restart Development Server

1. Stop the server (Ctrl+C or Cmd+C in terminal)
2. Start it again: `npm run dev`
3. Test the contact form on http://localhost:3000

**The contact form should now work!** Submit a test message and check your email.

## 🛠️ Development Guide

### Available Commands

| Command | What it does | When to use |
|---------|--------------|-------------|
| `npm run dev` | Starts development server | Daily development |
| `npm run build` | Creates production build | Before deploying |
| `npm run start` | Runs production build | Test before deployment |
| `npm run lint` | Checks code for errors | Before committing changes |

### Development Workflow

```bash
# 1. Start development
npm run dev

# 2. Make changes in src/ folder
# Changes appear automatically in browser

# 3. Before committing, check for errors
npm run lint

# 4. Test production build
npm run build
npm run start

# 5. If all good, commit your changes!
git add .
git commit -m "Description of changes"
```
## 📁 Project Structure Explained

Understanding where everything is located:

```
ecap-nextjs/
├── src/                        # All source code lives here
│   ├── app/                    # Next.js App Router (pages & layouts)
│   │   ├── layout.tsx         # Root layout (wraps all pages)
│   │   ├── page.tsx           # Home page (main entry point)
│   │   ├── globals.css        # Global styles & Tailwind imports
│   │   └── favicon.ico        # Website icon
│   │
│   ├── components/             # Reusable UI components
│   │   ├── layout/            # Page layout components
│   │   │   ├── Header.tsx     # Top navigation bar
│   │   │   └── Footer.tsx     # Bottom footer
│   │   │
│   │   └── sections/          # Homepage sections
│   │       ├── Hero.tsx       # Top banner with main message
│   │       ├── About.tsx      # About E-CAP section
│   │       ├── Programs.tsx   # Programs offered
│   │       ├── Impact.tsx     # Impact statistics
│   │       ├── Partners.tsx   # Partner institutions
│   │       ├── Team.tsx       # Team members
│   │       └── Contact.tsx    # Contact form
│   │
│   └── hooks/                 # Custom React hooks
│       └── useInView.ts       # Detects when element is visible
│
├── public/                     # Static files (images, etc.)
│   └── images/                # All images
│       ├── partners/          # Partner logos
│       └── members/           # Team member photos
│
├── .env.local                 # Environment variables (create this!)
├── tailwind.config.ts         # Tailwind CSS configuration
├── next.config.js             # Next.js configuration
├── tsconfig.json              # TypeScript configuration
├── package.json               # Project dependencies & scripts
└── README.md                  # This file
```

### Key Files Explained

#### `src/app/page.tsx`
The main homepage. This imports and displays all the sections:
```tsx
- Hero (banner)
- About
- Programs
- Impact
- Partners
- Team
- Contact
```

#### `src/app/layout.tsx`
Wraps all pages. Contains:
- HTML structure
- Header (navigation)
- Footer
- Metadata (for SEO)

#### `src/components/sections/[Section].tsx`
Each section is a separate component. Makes it easy to:
- Find and edit specific content
- Reuse components
- Keep code organized

#### `src/app/globals.css`
Global styles including:
- Tailwind CSS imports
- Custom CSS variables (colors)
- Font imports
- Animation definitions

#### `tailwind.config.ts`
Customizes Tailwind CSS:
- Color palette
- Font families
- Breakpoints (mobile/tablet/desktop)
- Animations

## 🎨 Design System

The website uses a carefully designed color palette and typography system.

### Color Palette

```css
Primary (Warm Orange)     #E87424  - Action buttons, links
Earth Brown              #8B4513  - Headings, trust
Earth Medium             #A0522D  - Text accents
Earth Light              #DEB887  - Backgrounds

Ocean Blue               #006994  - Growth, possibility
Ocean Medium             #0088C7  - Interactive elements
Ocean Light              #4AB8E8  - Accents

Coral                    #FF6B47  - Energy, impact
Warm Cream               #FAF3E0  - Section backgrounds
```

### Typography

| Font Family | Used For | Why |
|-------------|----------|-----|
| **Playfair Display** | Headings (h1, h2) | Elegant, authoritative |
| **Commissioner** | Body text | Readable, modern |
| **Work Sans** | Buttons, UI | Clear, functional |
| **Mukta Malar** | Tamil text | Native language support |

### Using the Design System

In your components, use these Tailwind classes:

```tsx
// Buttons
<button className="btn-primary">Click Me</button>
<button className="btn-secondary">Learn More</button>

// Headings
<h1 className="heading-1">Main Title</h1>
<h2 className="heading-2">Section Title</h2>
<h3 className="heading-3">Subsection</h3>

// Text
<p className="body-large">Important paragraph</p>
<p className="text-earth-600">Regular text</p>

// Cards with hover effect
<div className="card-hover">Content</div>
```

These classes are defined in `globals.css` and `tailwind.config.ts`.

## 📝 How to Update Content

This section shows you how to make common changes to the website.

### Editing Text Content

All content is in component files in `src/components/sections/`. Here's how to update each section:

#### 1. Hero Section (Top Banner)

**File**: [src/components/sections/Hero.tsx](src/components/sections/Hero.tsx)

Find and edit:
```tsx
<h1>Employment Career Awareness Program</h1>
<p>Your mission statement here</p>
```

**What you can change**:
- Main heading
- Subtitle/mission statement
- Button text
- Background image

#### 2. About Section

**File**: [src/components/sections/About.tsx](src/components/sections/About.tsx)

Update the description text and stats:
```tsx
const stats = [
  { number: '1000+', label: 'Students Guided' },
  // Edit these numbers and labels
];
```

#### 3. Programs Section

**File**: [src/components/sections/Programs.tsx](src/components/sections/Programs.tsx)

Add or modify programs:
```tsx
const programs = [
  {
    title: 'Program Name',
    description: 'Program description',
    icon: <GraduationCap />, // Choose icon
  },
  // Add more programs here
];
```

#### 4. Team Section

**File**: [src/components/sections/Team.tsx](src/components/sections/Team.tsx)

Add team members:
```tsx
const teamMembers = [
  {
    name: 'John Doe',
    role: 'Founder & Director',
    bio: 'Short bio about the person',
    image: '/images/members/john.jpg', // Add image first!
    linkedin: 'https://linkedin.com/in/johndoe',
    email: 'john@example.com',
  },
  // Add more team members...
];
```

**Steps to add a team member**:
1. Add their photo to `public/images/members/`
2. Add their details in the array above
3. Save the file
4. Check the website - they appear automatically!

#### 5. Partners Section

**File**: [src/components/sections/Partners.tsx](src/components/sections/Partners.tsx)

Add partner institutions:
```tsx
const partners = [
  {
    name: 'Partner Name',
    logo: '/images/partners/logo.png',
    website: 'https://partner-website.com',
  },
  // Add more partners...
];
```

#### 6. Contact Section

**File**: [src/components/sections/Contact.tsx](src/components/sections/Contact.tsx)

Update contact information:
```tsx
const contactInfo = [
  { icon: <Mail />, label: 'Email', value: 'your@email.com' },
  { icon: <Phone />, label: 'Phone', value: '+91 XXXXX XXXXX' },
  // Update these values
];
```

### Adding or Updating Images

#### Step 1: Prepare Your Image

- **Format**: JPG, PNG, or WebP
- **Size**: Recommended max 2MB per image
- **Dimensions**: 
  - Team photos: 400x400px (square)
  - Partner logos: 200x100px (landscape)
  - Hero images: 1920x1080px

#### Step 2: Add to Public Folder

Place images in the appropriate folder:
```
public/images/
├── members/       ← Team member photos
├── partners/      ← Partner logos
└── hero/          ← Banner images
```

#### Step 3: Reference in Code

Use the Next.js Image component for automatic optimization:

```tsx
import Image from 'next/image';

<Image 
  src="/images/members/john.jpg"
  alt="John Doe - Founder"
  width={400}
  height={400}
  className="rounded-full"
/>
```

**Why use Next.js Image?**
- Automatically optimizes images
- Lazy loading (loads when scrolling into view)
- Responsive sizes for different devices
- WebP format conversion

### Changing Colors

#### Quick Color Changes

Edit `tailwind.config.ts` to change the color scheme:

```typescript
colors: {
  primary: {
    DEFAULT: '#E87424',  // Change this hex code
    50: '#FEF5F0',       // Lighter shade
    900: '#6B3210',      // Darker shade
  },
  // ... more colors
}
```

#### Finding Colors

Use these tools to pick colors:
- [Coolors.co](https://coolors.co/) - Color palette generator
- [Adobe Color](https://color.adobe.com/) - Color wheel
- [Tailwind Color Shades](https://www.tints.dev/) - Generate shades

### Changing Fonts

#### Step 1: Find a Font

Browse [Google Fonts](https://fonts.google.com/) for free fonts.

#### Step 2: Import in globals.css

Add to `src/app/globals.css`:
```css
@import url('https://fonts.googleapis.com/css2?family=Your+Font+Name:wght@400;600;700&display=swap');
```

#### Step 3: Update Tailwind Config

Add to `tailwind.config.ts`:
```typescript
fontFamily: {
  'your-font': ['Your Font Name', 'sans-serif'],
}
```

#### Step 4: Use in Components

```tsx
<h1 className="font-your-font">Heading</h1>
```

## � Deployment Guide

Ready to publish your website? Here are the best options:

### Option 1: Vercel (Recommended - Easiest!)

**Why Vercel?**
- Made by the creators of Next.js
- Free for personal/NGO projects
- Automatic deployments from Git
- Built-in SSL certificate (HTTPS)
- Great performance (CDN)

**Steps to Deploy**:

1. **Push your code to GitHub**
   ```bash
   # If not already a git repo
   git init
   git add .
   git commit -m "Initial commit"
   
   # Create repo on GitHub, then:
   git remote add origin https://github.com/yourusername/ecap-website.git
   git push -u origin main
   ```

2. **Sign up for Vercel**
   - Go to [vercel.com](https://vercel.com)
   - Click "Sign Up"
   - Choose "Continue with GitHub"

3. **Import your project**
   - Click "Add New Project"
   - Select your GitHub repository
   - Vercel auto-detects Next.js settings ✓

4. **Add environment variables**
   - Before deploying, click "Environment Variables"
   - Add your EmailJS credentials:
     ```
     NEXT_PUBLIC_EMAILJS_SERVICE_ID = your_service_id
     NEXT_PUBLIC_EMAILJS_TEMPLATE_ID = your_template_id
     NEXT_PUBLIC_EMAILJS_PUBLIC_KEY = your_public_key
     ```

5. **Deploy!**
   - Click "Deploy"
   - Wait 1-2 minutes
   - Your site is live! 🎉

**Future Updates**:
- Just push to GitHub: `git push`
- Vercel automatically redeploys
- Preview each deployment before making it live

### Option 2: Netlify

Similar to Vercel, also free and easy:

1. Push code to GitHub
2. Go to [netlify.com](https://netlify.com)
3. "Add new site" → "Import from Git"
4. Select repository
5. Build command: `npm run build`
6. Publish directory: `.next`
7. Add environment variables
8. Deploy!

### Option 3: Traditional Hosting

For shared hosting (cPanel, etc.):

1. **Build the project**
   ```bash
   npm run build
   ```

2. **Export as static files** (if needed)
   Update `next.config.js`:
   ```js
   module.exports = {
     output: 'export',
   }
   ```

3. **Upload the `out/` folder** to your hosting

**Note**: Some features may not work without Node.js server.

### Custom Domain

To use your own domain (e.g., www.ecap.org):

**On Vercel/Netlify**:
1. Go to project settings
2. Add your domain
3. Update DNS records at your domain registrar:
   ```
   Type: CNAME
   Name: www
   Value: [provided by Vercel/Netlify]
   ```

## 📱 Responsive Design

The website automatically adapts to different screen sizes using Tailwind breakpoints:

```css
/* Mobile First - default styles are for mobile */
sm:  640px   /* Small tablets */
md:  768px   /* Tablets */
lg:  1024px  /* Laptops */
xl:  1280px  /* Desktops */
2xl: 1536px  /* Large desktops */
```

**Example**:
```tsx
<div className="text-sm md:text-base lg:text-lg">
  {/* Small text on mobile, larger on tablet, even larger on desktop */}
</div>
```

## ♿ Accessibility Features

The website includes:

- ✅ **Semantic HTML**: Uses proper heading hierarchy (h1, h2, h3)
- ✅ **ARIA labels**: For screen readers
- ✅ **Keyboard navigation**: All interactive elements accessible via keyboard
- ✅ **Focus indicators**: Visible focus states for keyboard users
- ✅ **Alt text**: All images have descriptive alt text
- ✅ **Color contrast**: Meets WCAG AA standards
- ✅ **Responsive text**: Scalable fonts for readability

**Testing Accessibility**:
- Use keyboard only (Tab, Enter, Escape keys)
- Test with screen reader (VoiceOver on Mac, NVDA on Windows)
- Check contrast with [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)

## ⚡ Performance Optimization

The website is optimized for speed:

### Built-in Optimizations

- ✅ **Image optimization**: Next.js automatically optimizes images
- ✅ **Code splitting**: Only loads necessary JavaScript
- ✅ **Lazy loading**: Images load as you scroll
- ✅ **Minification**: Production code is compressed
- ✅ **Font optimization**: Google Fonts are optimized

### Testing Performance

Use these tools:
- [PageSpeed Insights](https://pagespeed.web.dev/) - Google's performance tool
- [GTmetrix](https://gtmetrix.com/) - Detailed performance report
- Chrome DevTools Lighthouse (F12 → Lighthouse tab)

**Target Scores**:
- Performance: 90+
- Accessibility: 95+
- Best Practices: 95+
- SEO: 95+

## 🐛 Troubleshooting Guide

Common issues and how to fix them:

### ❌ Issue: Port 3000 is already in use

**Error message**: `Port 3000 is already in use`

**Solution 1: Kill the process**
```bash
# On Mac/Linux
lsof -ti:3000 | xargs kill -9

# On Windows
netstat -ano | findstr :3000
taskkill /PID [process_id] /F
```

**Solution 2: Use a different port**
```bash
npm run dev -- -p 3001
# Now visit http://localhost:3001
```

### ❌ Issue: npm install fails

**Error**: Various errors during `npm install`

**Solution 1: Clear cache and retry**
```bash
# Clear npm cache
npm cache clean --force

# Delete existing files
rm -rf node_modules package-lock.json

# Reinstall
npm install
```

**Solution 2: Update Node.js**
- Check version: `node --version`
- Need 18.0.0 or higher
- Download from [nodejs.org](https://nodejs.org/)

**Solution 3: Use npm instead of yarn/pnpm**
```bash
# Delete lock files
rm -f yarn.lock pnpm-lock.yaml

# Use npm
npm install
```

### ❌ Issue: Build errors

**Error**: `npm run build` fails

**Solution 1: Clear Next.js cache**
```bash
# Delete build cache
rm -rf .next

# Rebuild
npm run build
```

**Solution 2: Check for TypeScript errors**
```bash
# Run type check
npx tsc --noEmit

# Fix any errors shown
```

**Solution 3: Check for syntax errors**
- Look at the error message
- It usually shows the file and line number
- Common issues:
  - Missing closing tags `</div>`
  - Missing imports `import { Component } from 'library'`
  - Typos in variable names

### ❌ Issue: EmailJS not working

**Error**: Contact form doesn't send emails

**Checklist**:
1. ✅ EmailJS account created?
2. ✅ Email service connected?
3. ✅ Email template created?
4. ✅ `.env.local` file exists?
5. ✅ Environment variables correct?
6. ✅ Server restarted after adding `.env.local`?

**Debug steps**:

```bash
# 1. Check if .env.local exists
ls -la .env.local

# 2. Display variables (without values)
cat .env.local

# 3. Should see:
# NEXT_PUBLIC_EMAILJS_SERVICE_ID=...
# NEXT_PUBLIC_EMAILJS_TEMPLATE_ID=...
# NEXT_PUBLIC_EMAILJS_PUBLIC_KEY=...
```

**Still not working?**
- Open browser console (F12)
- Try submitting the form
- Look for red error messages
- Copy error and search on Google

### ❌ Issue: Images not showing

**Error**: Image appears broken or doesn't load

**Common causes**:

1. **Wrong path**
   ```tsx
   ❌ <Image src="images/photo.jpg" />
   ✅ <Image src="/images/photo.jpg" />  // Note the leading /
   ```

2. **Image doesn't exist**
   - Check file actually exists in `public/images/`
   - Check spelling (case-sensitive!)

3. **Wrong image format**
   - Use: JPG, PNG, WebP, SVG
   - Convert other formats using online tools

4. **Missing width/height**
   ```tsx
   ❌ <Image src="/images/photo.jpg" />
   ✅ <Image src="/images/photo.jpg" width={400} height={300} />
   ```

### ❌ Issue: Changes not appearing

**Problem**: Made changes but don't see them in browser

**Solutions**:

1. **Hard refresh the browser**
   - Mac: Cmd + Shift + R
   - Windows: Ctrl + Shift + R
   - Or Ctrl+F5

2. **Check if dev server is running**
   ```bash
   # Should see "Ready in Xms"
   # If not, start it:
   npm run dev
   ```

3. **Check for errors in terminal**
   - Look at the terminal where `npm run dev` is running
   - Red error messages? Fix them first

4. **Clear browser cache**
   - Open DevTools (F12)
   - Right-click refresh button
   - Choose "Empty cache and hard reload"

### ❌ Issue: Styling not working

**Problem**: Tailwind classes not applying

**Solutions**:

1. **Check class name spelling**
   ```tsx
   ❌ <div className="text-centre">  // "centre" is wrong
   ✅ <div className="text-center">  // "center" is correct
   ```

2. **Incorrect dynamic classes**
   ```tsx
   ❌ <div className={`text-${color}-500`}>  // Won't work
   ✅ <div className={color === 'blue' ? 'text-blue-500' : 'text-red-500'}>
   ```

3. **Missing Tailwind import**
   - Check `src/app/globals.css` has:
   ```css
   @tailwind base;
   @tailwind components;
   @tailwind utilities;
   ```

4. **Rebuild Tailwind**
   ```bash
   # Restart dev server
   Ctrl+C  # Stop current server
   npm run dev  # Start again
   ```

### ❌ Issue: TypeScript errors

**Error**: Red squiggly lines in VS Code

**Common fixes**:

1. **Reload VS Code TypeScript**
   - Press: Cmd/Ctrl + Shift + P
   - Type: "TypeScript: Restart TS Server"
   - Press Enter

2. **Install types**
   ```bash
   npm install --save-dev @types/react @types/node
   ```

3. **Check tsconfig.json**
   - Should exist in project root
   - Restart VS Code if you just created it

### 🆘 Still Having Issues?

1. **Read the error message carefully**
   - Often tells you exactly what's wrong
   - Includes file name and line number

2. **Search the error on Google**
   - Copy the error message
   - Add "Next.js" to the search
   - Check Stack Overflow results

3. **Check Next.js documentation**
   - [Next.js Docs](https://nextjs.org/docs)
   - Very comprehensive and searchable

4. **Ask for help**
   - Next.js Discord: [discord.gg/nextjs](https://discord.gg/nextjs)
   - Stack Overflow: Tag with `next.js`
   - GitHub Issues: Check if it's a known bug

## 💡 Tips for Beginners

### Learning Path

1. **Week 1: Get familiar**
   - Run the project locally
   - Make simple text changes
   - Understand the folder structure

2. **Week 2: Content updates**
   - Update team members
   - Change colors
   - Add new images

3. **Week 3: Component changes**
   - Modify existing components
   - Understand props and state
   - Learn React basics

4. **Week 4: New features**
   - Add new sections
   - Integrate new libraries
   - Deploy to production

### Best Practices

✅ **DO**:
- Make small changes and test frequently
- Commit to Git after each working feature
- Use meaningful commit messages
- Read error messages carefully
- Ask for help when stuck

❌ **DON'T**:
- Make many changes at once
- Ignore warnings and errors
- Edit `node_modules/` folder
- Commit `.env.local` to Git
- Give up! Everyone starts as a beginner

### Useful Resources

**React & Next.js**:
- [React Docs](https://react.dev) - Official React documentation
- [Next.js Learn](https://nextjs.org/learn) - Interactive tutorial
- [React Tutorial](https://react-tutorial.app/) - Hands-on exercises

**Tailwind CSS**:
- [Tailwind Docs](https://tailwindcss.com/docs) - All available classes
- [Tailwind Cheat Sheet](https://nerdcave.com/tailwind-cheat-sheet) - Quick reference

**JavaScript/TypeScript**:
- [MDN Web Docs](https://developer.mozilla.org/) - Best JS reference
- [TypeScript Handbook](https://www.typescriptlang.org/docs/) - Learn TypeScript
- [JavaScript.info](https://javascript.info/) - Modern JavaScript tutorial

**Tools**:
- [VS Code Setup](https://code.visualstudio.com/docs/nodejs/reactjs-tutorial) - Editor setup
- [Git Tutorial](https://www.atlassian.com/git/tutorials) - Learn Git basics

## 🤝 Contributing to the Project

We welcome contributions! Whether you're fixing bugs, adding features, or improving documentation.

### How to Contribute

1. **Fork or Branch**
   ```bash
   # Create a new branch for your changes
   git checkout -b feature/your-feature-name
   
   # Or for bug fixes
   git checkout -b fix/issue-description
   ```

2. **Make Your Changes**
   - Edit the necessary files
   - Test thoroughly with `npm run dev`
   - Ensure no errors with `npm run build`

3. **Commit Your Changes**
   ```bash
   git add .
   git commit -m "Add: clear description of what you added"
   # Or
   git commit -m "Fix: description of what you fixed"
   ```

4. **Push and Create Pull Request**
   ```bash
   git push origin feature/your-feature-name
   ```

### Commit Message Guidelines

Use clear, descriptive commit messages:

```bash
# Good examples:
git commit -m "Add: Team member photo gallery"
git commit -m "Fix: Contact form validation error"
git commit -m "Update: Hero section text and styling"
git commit -m "Remove: Unused partner logo"

# Bad examples:
git commit -m "changes"
git commit -m "fix stuff"
git commit -m "update"
```

### Code Style

- Use **TypeScript** for new files
- Follow existing code patterns
- Use **Tailwind** classes instead of custom CSS when possible
- Add comments for complex logic
- Keep components small and focused

### Testing Checklist

Before submitting changes, verify:

- [ ] Code runs without errors: `npm run dev`
- [ ] Production build works: `npm run build`
- [ ] No linting errors: `npm run lint`
- [ ] Tested on mobile (use browser DevTools)
- [ ] Checked all affected pages
- [ ] Images load correctly
- [ ] Links work properly
- [ ] Forms submit successfully

## 📊 Project Tech Stack Summary

| Category | Technology | Version |
|----------|------------|---------|
| **Framework** | Next.js | 14.1.0 |
| **UI Library** | React | 18.2.0 |
| **Language** | TypeScript | 5.3.3 |
| **Styling** | Tailwind CSS | 3.4.1 |
| **Animations** | Framer Motion | 11.0.3 |
| **Icons** | Lucide React | 0.344.0 |
| **Email** | EmailJS Browser | 4.3.3 |
| **Deployment** | Vercel | - |

## 📄 License & Credits

### License

This project is created for **E-CAP NGO**. All rights reserved.

### Credits

**Built For**:
- E-CAP (Employment Career Awareness Program)
- என்னும் வழிகாட்டி

**Technologies Used**:
- [Next.js](https://nextjs.org/) - React framework by Vercel
- [React](https://react.dev/) - UI library by Meta
- [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS framework
- [Framer Motion](https://www.framer.com/motion/) - Animation library
- [EmailJS](https://www.emailjs.com/) - Email service
- [Lucide Icons](https://lucide.dev/) - Beautiful icon library

**Fonts**:
- [Playfair Display](https://fonts.google.com/specimen/Playfair+Display) - Claus Eggers Sørensen
- [Commissioner](https://fonts.google.com/specimen/Commissioner) - Kostas Bartsokas
- [Work Sans](https://fonts.google.com/specimen/Work+Sans) - Wei Huang
- [Mukta Malar](https://fonts.google.com/specimen/Mukta+Malar) - Ek Type

**Hosting**:
- [Vercel](https://vercel.com/) - Deployment and hosting

## 📞 Contact & Support

### E-CAP NGO
- **Email**: ecapofficial@outlook.com
- **Phone**: +91 97864 06411
- **Mission**: Empowering students towards successful careers

### Technical Support

**For Developers**:
- Check this README first
- Search [Next.js Documentation](https://nextjs.org/docs)
- Ask on [Next.js Discord](https://discord.gg/nextjs)
- Post on [Stack Overflow](https://stackoverflow.com/questions/tagged/next.js)

**For E-CAP Team**:
- Content updates: Edit files in `src/components/sections/`
- Image updates: Add to `public/images/`
- Contact the developer if you need help

## 🗺️ Roadmap

Future enhancements planned:

### Phase 1 (Current)
- [x] Complete all sections
- [x] Responsive design
- [x] Contact form integration
- [ ] Complete image migration
- [ ] Deploy to production

### Phase 2 (Future)
- [ ] Blog section for articles
- [ ] Event calendar
- [ ] Success stories page
- [ ] Photo gallery
- [ ] Resource library for students
- [ ] Online registration forms

### Phase 3 (Advanced)
- [ ] Multi-language support (Tamil, English)
- [ ] Admin dashboard for content management
- [ ] Analytics integration
- [ ] SEO optimization
- [ ] Performance improvements
- [ ] Integration with social media

## 📊 Quick Reference

### Directory Cheat Sheet

```
Need to update...              → Edit this file...
────────────────────────────────────────────────────────────
Hero banner text               → src/components/sections/Hero.tsx
About section                  → src/components/sections/About.tsx
Programs list                  → src/components/sections/Programs.tsx
Team members                   → src/components/sections/Team.tsx
Partner logos                  → src/components/sections/Partners.tsx
Contact information            → src/components/sections/Contact.tsx
Header/navigation              → src/components/layout/Header.tsx
Footer links                   → src/components/layout/Footer.tsx
Colors                         → tailwind.config.ts
Global styles                  → src/app/globals.css
Add images                     → public/images/
EmailJS config                 → .env.local
```

### Command Cheat Sheet

```bash
npm run dev       # Start development (use this daily)
npm run build     # Create production build
npm run start     # Run production locally
npm run lint      # Check for errors

npm install       # Install all dependencies
git status        # Check what files changed
git add .         # Stage all changes
git commit -m ""  # Save changes
git push          # Upload to GitHub
```

### Tailwind CSS Common Classes

```css
/* Spacing */
p-4              Padding all sides
px-6 py-3        Padding horizontal/vertical
m-4              Margin all sides

/* Colors */
text-primary     Primary color text
bg-earth-50      Light earth background
border-ocean     Ocean blue border

/* Typography */
text-lg          Large text
font-bold        Bold weight
text-center      Center align

/* Layout */
flex             Flexbox container
grid             Grid container
hidden md:block  Hidden on mobile, show on tablet+

/* Effects */
hover:opacity-80     Hover effect
transition-all       Smooth transitions
rounded-lg           Rounded corners
```

---

## 🎉 You're Ready!

You now have all the information needed to work on the E-CAP website. Here's what to do next:

1. **Start the development server**: `npm run dev`
2. **Make a small change** to test your setup
3. **Explore the codebase** - look at different components
4. **Read through the sections** you'll be working on
5. **Ask for help** when you need it!

---

**Built with ❤️ for E-CAP - Empowering Students, Building Futures**

மாற்றத்திற்கான விதையாய் நாம் இருப்போம் (Let's be the seeds of change)

---

<div align="center">

**Questions?** Check the [Troubleshooting Guide](#-troubleshooting-guide) or reach out to ecapofficial@outlook.com

[🚀 Get Started](#-getting-started-for-beginners) • [📝 Update Content](#-how-to-update-content) • [🚢 Deploy](#-deployment-guide) • [🐛 Troubleshoot](#-troubleshooting-guide)

</div>
