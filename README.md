# Astro i18n Blog Example

This project demonstrates how to build a multi-language blog with [Astro](https://astro.build/).
It supports native URLs, a language switcher, and is easy to extend to new languages.

This is a good starting template for general Astro website like corporate, blog, landing page, etc.

I believe this is the best possible implementation of intenationalization for an Astro project for both native users and SEO.

---

## 💡 Strengths of This i18n Implementation

## (and Why This is Better then Astro Official Recipe)

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
| Language switcher | Simple path swap                 | Path mapping, Flag images, Native slugs |
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
  pages/
    en/        # English content
    ko/        # Korean content
    fr/        # French content
  components/
    Navigation.astro  # Language switcher and navigation
  layouts/
    BaseLayout.astro
    MarkdownPostLayout.astro
astro.config.mjs      # Astro config with i18n settings
```

---

## 🌍 How to Add a New Language

1. **Add your content:**  
   Copy one of the existing language folders (e.g., `en/`) and translate the files.  
   Place it in `src/pages/{your-lang-code}/`.

2. **Update the config:**

   - In `astro.config.mjs`, add your language code to the `locales` array.
   - In `src/components/Navigation.astro`, add your language to the `locales` array and to the `routeSlugs` mapping.

3. **(Optional) Change the default language:**  
   Edit `src/pages/index.astro` to redirect to your new default language:

   ```js
   ---
   return Astro.redirect('/es/');
   ---
   ```

4. **Done!**  
   The language switcher will update automatically.

---

## 🔄 How the Language Switcher Works

- The language switcher in the navigation bar is generated from a config array.
- When you add a new language to the config, it appears in the dropdown automatically.
- The switcher always links to the correct page in the selected language (if it exists).

---

## 🛠 Troubleshooting

- **404 when switching languages:**  
  Make sure you have added the correct slugs for each language in the `routeSlugs` mapping in `Navigation.astro`.
- **Language not showing in switcher:**  
  Check that you added your language to the `locales` array in `Navigation.astro` and to the `i18n.locales` array in `astro.config.mjs`.

---

## 📚 Further Reading

- [Astro Tutorial](https://docs.astro.build/en/tutorial/0-introduction/)
- [Astro Tutorial Code on GitHub](https://github.com/withastro/blog-tutorial-demo)

---
