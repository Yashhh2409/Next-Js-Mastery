# Next.js Notes 🚀

## 📌 Introduction
Next.js is a **React framework** that enables features like **server-side rendering** and **static site generation** for building fast and scalable web applications.

---

## 🎯 Features
✅ **File-based Routing** - Pages are created inside the `pages/` directory.
✅ **Pre-rendering** - Supports SSR (Server-Side Rendering) and SSG (Static Site Generation).
✅ **API Routes** - Backend functionality using API routes inside `pages/api/`.
✅ **Fast Refresh** - Instant feedback while developing.
✅ **Built-in CSS & Image Optimization** - Supports global styles, CSS modules, and automatic image optimization.
✅ **Middleware** - Run code before a request is completed.

---

## 📂 Project Setup
```sh
npx create-next-app@latest my-next-app
cd my-next-app
npm run dev
```
🛠 The development server runs at **http://localhost:3000**

---

## 📜 File-Based Routing
🔹 Each `.js` or `.tsx` file inside `pages/` becomes a route.
🔹 Example: `pages/about.js` can be accessed at `/about`.

```jsx
export default function About() {
  return <h1>About Page</h1>;
}
```

## 📜 Nested Routing
🔹 Each `.js` or `.tsx` file inside `app/blog/page.jsx` becomes a Nested route.
🔹 Example: `app/blog/about.jsx` can be accessed at `/blog/about.jsx`.

## 📜 Dynamic Routing
🔹 Each `.js` or `.tsx` file inside `app/blog/[id]/page.js` becomes a Dynamic route.
🔹 Example: `app/blog/[id]` can be accessed at `/blog/:id`.
🔹

```jsx
export default function BlogPost({ params }) {
  return <h1>Blog Post ID: {params.id}</h1>;
}
```


---

## ⚡ Pre-rendering Methods
### **1️⃣ Static Site Generation (SSG)** 🏗
- Generates HTML at build time.
- Use `getStaticProps` for data fetching.

```jsx
export async function getStaticProps() {
  return {
    props: { data: "Hello, World!" },
  };
}
```

### **2️⃣ Server-Side Rendering (SSR)** 🌎
- Fetches data at request time.
- Use `getServerSideProps`.

```jsx
export async function getServerSideProps() {
  return {
    props: { data: "Hello, SSR!" },
  };
}
```

---

## 🛠 API Routes
Create backend APIs inside `pages/api/`.
```jsx
export default function handler(req, res) {
  res.status(200).json({ message: "API is working!" });
}
```

---

## 🎨 Styling
✅ **Global CSS** - Add in `styles/globals.css`
✅ **CSS Modules** - Create component-specific styles: `styles/Home.module.css`
✅ **Tailwind CSS** - Install and configure easily.

```sh
npm install tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

---

## 🖼 Image Optimization
Use `next/image` for automatic image optimization.
```jsx
import Image from 'next/image';
<Image src="/logo.png" width={500} height={300} alt="Logo" />
```

---

## 🔥 Deployment
### **Vercel (Recommended) 🌍**
```sh
npm install -g vercel
vercel
```

### **Other Hosting Options**
- **Netlify**
- **GitHub Pages**
- **AWS, Firebase**

---

## 🏆 Best Practices
✅ Use **getStaticProps** whenever possible for better performance.
✅ Optimize images with `next/image`.
✅ Use **dynamic imports** to improve load time.
✅ Implement API caching for faster responses.

---

## 🎯 Conclusion
Next.js makes **React development easier, faster, and more scalable**! 🚀 Mastering it will boost your full-stack skills! 💪
