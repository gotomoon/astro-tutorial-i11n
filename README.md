# Astro Internationalization Implementation on Astro Official Tutorial Blog Project

This is an internationalization implementation of the Astro official tutorial.

- [Astro Tutorial](https://docs.astro.build/en/tutorial/0-introduction/)
- [Astro Tutorial Code on GitHub](https://github.com/withastro/blog-tutorial-demo)

If you have completed or are familiar with the official tutorial, this project will help you get started with internationalization quickly.

---

## Strengths of This i18n Implementation

### Why is this better than the Astro Official Internationalization Recipe?

I believe this approach provides the best possible experience for native users and the best implementation for SEO, for the following reasons:

- **User Experience:**  
  Native users see URLs in their own language (native URL), which is more user-friendly, as shown in the table below.  
  (Including Unicode handling of Chinese, Japanese, and Korean characters.)

| Language | URL                          |
| -------- | ---------------------------- |
| English  | `example.com/about`          |
| Korean   | `example.com/소개`           |
| Chinese  | `example.com/介绍`           |
| Japanese | `example.com/紹介`           |
| Spanish  | `example.com/sobre-nosotros` |
| French   | `example.com/a-propos`       |

- **SEO:**  
  Native slugs can improve SEO for native search terms.

- **Customization:**  
  This is a truly bilingual site with a native experience for both languages, not just a translation of English slugs.

- **Full Content Localization:**  
  Each language can have fully independent content. This is very important because native speakers notice subtle differences in the atmosphere of a page versus a cookie-cutter translation. This is crucial, especially for marketing websites.

- **Dynamic Routing:**  
  Works for both static and dynamic pages (tags, posts).

- **No External Dependencies:**  
  Simple, maintainable, and easy to extend.

- **Astro Flexibility:**  
  Astro's file-based routing allows for this flexibility, even though the official recipe uses romanized slugs for simplicity and universality.

- **Language Switcher That Just Works**

---

### Key Differences Between Astro Official Recipe and This Project

| Aspect            | Astro Official Recipe            | This Project                        |
| ----------------- | -------------------------------- | ----------------------------------- |
| Default language  | At root, romanized/English slugs | At root, native language slugs      |
| Other languages   | In subfolders (e.g., /en/, /fr/) | In /en/ subfolder                   |
| Slug style        | English/romanized                | Native language                     |
| Navigation        | English/romanized                | Native (English for /en)            |
| Language switcher | Simple path swap                 | Path mapping, supports native slugs |
| Dynamic routes    | English/romanized                | Native (English for /en)            |

---

### Summary Table of Implementation

Use the table below as a reference to customize for your language.

| Feature            | Korean (default)          | English (secondary)      |
| ------------------ | ------------------------- | ------------------------ |
| Main pages         | Native slugs (e.g., /홈)  | /en/ subfolder           |
| Blog posts         | /글/글-x.md               | /en/posts/post-x.md      |
| Tag pages          | /태그/인덱스, /태그/[tag] | /en/tags, /en/tags/[tag] |
| Navigation         | Korean links              | English links            |
| Language switcher  | Mapping logic             | Mapping logic            |
| Layouts/components | Shared                    | Shared                   |
| SEO/lang attribute | Dynamic                   | Dynamic                  |

---

# Instruction

To add a new language (e.g., Spanish, "es") to your Astro project, you only need to update a few configuration/code files after adding your new content under `/src/pages/es/`:

---

### **1. `astro.config.mjs`**

- Add the new language code to the `i18n.locales` array:
  ```js
  i18n: {
    locales: ["en", "ko", "fr", "es"], // Add "es"
    defaultLocale: "en",
    routing: {
      prefixDefaultLocale: true,
    },
  },
  ```

---

### **2. `src/components/Navigation.astro`**

- **Add the new language to the `locales` array**:
  ```js
  const locales = [
    { code: "en", label: "🇺🇸 English" },
    { code: "ko", label: "🇰🇷 한국어" },
    { code: "fr", label: "🇫🇷 Français" },
    { code: "es", label: "🇪🇸 Español" }, // Add this line
  ];
  ```
- **Add the new language's slugs to `routeSlugs`**:
  ```js
  const routeSlugs: Record<string, Record<string, string>> = {
    home: { en: "", ko: "", fr: "", es: "" },
    about: { en: "about", ko: "소개", fr: "a-propos", es: "acerca" },
    blog: { en: "blog", ko: "블로그", fr: "blog", es: "blog" },
    tags: { en: "tags", ko: "태그", fr: "tags", es: "etiquetas" },
  };
  ```
  - Make sure to provide the correct slug for each static page in the new language.
  - The language switcher is automatically updated and will immediately display the new language with the flag

---

### **3. Add Content**

- Add your new language content under `/src/pages/es/` (or your new language code), following the same structure as `/en/`, `/ko/`, and `/fr/`.

---

### **4. (Optional) Other Components**

If you want to change the default language, open /src/pages/index.astro and change the language folder name accordingly.

```
return Astro.redirect('/en/');
```

---

**You do NOT need to change any other files if your project is already using the config-driven approach for navigation and language switching.**

---

## **Summary Table**

| File/Location                     | What to Update                                  |
| --------------------------------- | ----------------------------------------------- |
| `/src/pages/{newlang}/`           | Add new language content (same structure)       |
| `astro.config.mjs`                | Add new language code to `i18n.locales`         |
| `src/components/Navigation.astro` | Add to `locales` array and `routeSlugs` mapping |
| (Optional) Other components       | Only if you have hardcoded language logic       |

---

**That’s it!**  
Add your content, update the config, and your site will support the new language everywhere—including the language switcher and navigation—without further code changes.

Let me know if you want a template for a new language or further automation!

```
  ---
  return Astro.redirect('/en/');
  ---
```

**DEMO:**  
https://astro-tutorial-i11n.vercel.app/en/
