# Astro Internationalization (i18n) Using Official Astro Tutorial

This project demonstrates how to build a multi-language blog with [Astro](https://astro.build/).

It supports native URLs, a language switcher, and is easy to extend to new languages.

This is a great starting template for multilingual corporate sites, blogs, landing pages, and more. Once your project is up and running, start adding styling and Astro islands incrementally.

You can easily get your project up and running and add new languages by following the instructions below, or by using them as prompts for AI tools.

I believe this is the best possible implementation of internationalization for an Astro project, both for native users and for SEO.

---

## 💡 Strengths of This i18n Implementation (And Why This Is Better Than the Astro Official Recipe)

- **User Experience:**  
  Native users see URLs in their own language (native URL), which is more user-friendly and SEO-friendly.
- **SEO:**  
  Native slugs can improve SEO for native search terms.
- **Customization:**  
  Each language can have fully independent content and navigation, which is often crucial for marketing websites.
- **Dynamic Routing:**  
  Works for both static and dynamic pages (tags, posts).
- **No External Dependencies:**  
  Simple, maintainable, and easy to extend.
- **Astro Flexibility:**  
  Astro's file-based routing allows for this flexibility.
- **Language Switcher That Just Works**

---

## 🔎 Key Differences: Astro Official Recipe vs. This Project

| Aspect            | Astro Official Recipe            | This Project                            |
| ----------------- | -------------------------------- | --------------------------------------- |
| Default language  | At root, romanized/English slugs | At root, native language slugs          |
| Slug style        | English/romanized                | Native language                         |
| Navigation        | English/romanized                | Native language                         |
| Language switcher | Simple path swap                 | Path mapping, flag images, native slugs |
| Dynamic routes    | English/romanized                | Native language                         |

---

**DEMO:**  
https://astro-tutorial-i11n.vercel.app/en/

---

## 🚀 Quick Start

1. **Install dependencies:**
   ```bash
   npm install
   # or
   yarn
   ```
2. **Start the dev server:**
   ```bash
   npm run dev
   # or
   yarn dev
   ```
3. **Open your browser:**  
   Go to [http://localhost:4321](http://localhost:4321) (or the port shown in your terminal).
4. **Switch languages:**  
   Use the dropdown in the navigation bar to view the site in English, Korean, or French.

---

## 🗂 Project Structure

```
src/
├── pages/
│   ├── en/        # English content
│   ├── ko/        # Korean content
│   └── fr/        # French content
├── components/
│   └── Navigation.astro  # Language switcher and navigation
├── layouts/
│   ├── BaseLayout.astro
│   └── MarkdownPostLayout.astro
astro.config.mjs      # Astro config with i18n settings
```
