# Sheng How Kong | Cloud/Backend Engineer Portfolio

A premium, interactive terminal-themed web portfolio showcasing software development experience, skill set, and contact details. Built with Nuxt 4, Vue 3, and a custom design system styled for visual excellence and responsiveness.

---

## 🎨 Design Features

- **Interactive Terminal Theme**: Terminal console UI featuring customized output rendering for commands like `whoami`, `ls ./skills`, and `cat ./experience.log`.
- **Visually Optimized & Responsive**: Fully responsive layout with mobile-first break points ensuring a clean UI presentation on devices ranging from smartphones (e.g. iPhone SE) to wide-screen displays.
- **Glassmorphism & Radial Gradients**: Modern dark theme aesthetics utilizing radial gradient backing, transluscent surface panels, and custom glowing elements.
- **Micro-Animations**: Blinking typing cursors and sleek translation animations on badge interactive cards.

---

## 🛠️ Stack & Technologies

- **Framework**: [Nuxt 4](https://nuxt.com/) (Vue 3)
- **Styling**: Plain CSS with custom properties for consistent design tokens
- **Icons & Fonts**: JetBrains Mono & Inter Google Fonts
- **Package Manager**: Bun (or npm/pnpm/yarn)

---

## 💻 Getting Started

### 1. Installation

Install the project dependencies using Bun (recommended) or your preferred package manager:

```bash
# Using Bun
bun install

# Or using npm
npm install
```

### 2. Development

Launch the hot-reloading development server:

```bash
# Using Bun
bun run dev

# Or using npm
npm run dev
```

The application will be available at `http://localhost:3000`.

### 3. Build & Production

To build the static application bundle or preview the production deployment:

```bash
# Generate static HTML pages
bun run generate

# Preview production build locally
bun run preview
```

The generated static output will reside in `.output/public`.

---

## 📁 Repository Structure

```text
shenghow95-portfolio/
├── app/
│   ├── assets/
│   │   └── css/
│   │       └── main.css      # Core global stylesheet & design system
│   ├── components/
│   │   ├── ExperienceCard.vue # Customized layout block for jobs
│   │   └── SkillBadge.vue     # Dynamic inline badges
│   ├── pages/
│   │   ├── index.vue          # Interactive console landing page
│   │   └── resume.vue         # Professional resume view
│   └── app.vue                # Main layout mounting
├── nuxt.config.ts             # Nuxt configurations & metadata
└── package.json
```
