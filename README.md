# E-CAP NGO Website

> **Employment Career Awareness Program (என்னும் வழிகாட்டி)** - Official website for a non-profit organization dedicated to guiding students towards successful careers.

**Maintainer**: [@varshathgupta](https://github.com/varshathgupta)

## File Structure

```
ecap/
├── ecap-nextjs/           # Main Next.js application
│   ├── src/
│   │   ├── app/           # Pages and layouts
│   │   │   ├── globals.css
│   │   │   ├── layout.tsx
│   │   │   └── page.tsx
│   │   ├── components/    # Reusable UI components
│   │   │   ├── layout/
│   │   │   │   ├── Footer.tsx
│   │   │   │   └── Header.tsx
│   │   │   └── sections/
│   │   │       ├── About.tsx
│   │   │       ├── Contact.tsx
│   │   │       ├── Hero.tsx
│   │   │       ├── Impact.tsx
│   │   │       ├── Partners.tsx
│   │   │       ├── Programs.tsx
│   │   │       └── Team.tsx
│   │   └── hooks/         # Custom React hooks
│   │       └── useInView.ts
│   ├── public/            # Static files and images
│   │   └── images/
│   │       └── members/
│   ├── package.json       # Dependencies and scripts
│   ├── next.config.js     # Next.js configuration
│   ├── tailwind.config.ts # Tailwind CSS configuration
│   └── tsconfig.json      # TypeScript configuration
├── README.md              # This file
└── SKILL.md               # Design guidelines
```

## Setup Instructions

### Prerequisites

- Node.js (version 18 or higher)
- Git

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/ecap-team/landing-page.git
   cd ecap
   ```

2. **Navigate to the project directory**
   ```bash
   cd ecap-nextjs
   ```

3. **Install dependencies**
   ```bash
   npm install
   ```

4. **Start development server**
   ```bash
   npm run dev
   ```

5. **Open in browser**
   
   Visit http://localhost:3000

### Available Commands

| Command | Description |
|---------|-------------|
| `npm run dev` | Start development server |
| `npm run build` | Create production build |
| `npm run start` | Run production build locally |
| `npm run lint` | Check for code errors |

## Git Workflow

### Creating a Branch

1. **Create and switch to a new branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```
   
   Branch naming conventions:
   - `feature/` - New features (e.g., `feature/contact-form`)
   - `fix/` - Bug fixes (e.g., `fix/mobile-nav`)
   - `docs/` - Documentation updates (e.g., `docs/readme-update`)

2. **Make your changes**
   
   Edit files as needed and test locally with `npm run dev`

3. **Stage and commit changes**
   ```bash
   git add .
   git commit -m "Description of your changes"
   ```

4. **Push branch to GitHub**
   ```bash
   git push origin feature/your-feature-name
   ```

### Creating a Pull Request and Adding Reviewer

1. **Create Pull Request on GitHub**
   - Go to the repository on GitHub
   - Click "Pull requests" → "New pull request"
   - Select your branch to merge into `main`
   - Click "Create pull request"
   - Add a descriptive title and description

2. **Add Reviewer**
   - On the Pull Request page, look for "Reviewers" in the right sidebar
   - Click the gear icon ⚙️ next to "Reviewers"
   - Search for and select **@varshathgupta**
   - Wait for review approval before merging

### Important Notes

- Always create a new branch for your changes (never commit directly to `main`)
- Test your changes locally before pushing
- Add **@varshathgupta** as a reviewer on all pull requests
- Wait for approval before merging

---

**Built with ❤️ for E-CAP - Empowering Students, Building Futures**
