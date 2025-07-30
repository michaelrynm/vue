# Landing Page

A responsive and animated landing page built with **Vue 3**, **Vite**, and **GSAP**. This project serves as a clean and minimal template for showcasing products, portfolios, or marketing campaigns. Designed to be fast, responsive, and easy to customize.

---

## 🚀 Features

- ⚡️ Powered by [Vue 3](https://vuejs.org/) and [Vite](https://vitejs.dev/)
- 🎞 Smooth and dynamic animations using [GSAP](https://greensock.com/gsap/)
- 📱 Fully responsive layout for all devices
- 🎨 Modular and maintainable component structure
- 🧩 Built with scoped Sass styles

---

## 🛠 Technologies Used

- **Vue 3** – Progressive front-end framework
- **Vite** – Lightning-fast build tool
- **GSAP** – JavaScript animation library
- **Sass** – CSS preprocessor for custom styling
- *(Optional)* Tailwind CSS – If added manually

---

## 🧰 System Requirements

To run this project locally, make sure you have the following installed:

- **Node.js** `>= 16.x`  
- **npm** `>= 8.x` or **Yarn** `>= 1.22`
- Recommended: [VSCode](https://code.visualstudio.com/) with the extension for Vue 3 support

To check your versions:

```bash
node -v
npm -v
```

---

## 📁 Folder Structure Overview
```bash
src/
├── assets/             # Images, fonts, icons
├── components/         # Reusable Vue components
├── pages/              # Page-level views
├── App.vue             # Main application shell
├── main.js             # App entry point
```

---
## 📦 Project Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/landing-page.git
cd landing-page
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Run in development mode

```bash
npm run dev
```

### package.json
```bash
{
  "name": "landing-page",
  "version": "0.0.0",
  "private": true,
  "type": "module",
  "engines": {
    "node": "^20.19.0 || >=22.12.0"
  },
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview",
    "format": "prettier --write src/"
  },
  "dependencies": {
    "gsap": "^3.13.0",
    "vue": "^3.5.18"
  },
  "devDependencies": {
    "@vitejs/plugin-vue": "^6.0.1",
    "prettier": "3.6.2",
    "sass": "^1.89.2",
    "sass-loader": "^16.0.5",
    "vite": "^7.0.6",
    "vite-plugin-vue-devtools": "^8.0.0"
  }
}
```

## 📸 Live Demo
[Live Demo](https://vue-vert-pi.vercel.app/)

