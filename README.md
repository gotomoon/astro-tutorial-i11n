# Astro Internalization Implementation on Astro Official Tutorial Blog Project"

This is internalization implementation of the Astro official tutorial.

- [Astro Tutorial](https://docs.astro.build/en/tutorial/0-introduction/)

- [Astro Tutorial Code in Github](https://github.com/withastro/blog-tutorial-demo).

If you completed or familiar with the official tutorial, this project should get you started with internationalization fast.

This project is a biliangual website with Korean as the default language and English as the second language. However, you should be able to add and change the languages easily.

# Strengths of This i18n Implementation

- Native URLs: Korean users see URLs in their own language, which is user-friendly and good for SEO.
- Full content localization: Each language can have fully independent content.
- Dynamic routing: Works for both static and dynamic pages (tags, posts).
- No external dependencies: Simple, maintainable, and easy to extend.

- Lanuage switcher that just works
- Localized slugs (Localized URLs): users see URLs in their own language, which is user-friendly and maximizes SEO
  (including Unicode handling of Chinese, Japanese, and Korean characters)

| Language | URL                          |
| -------- | ---------------------------- |
| English  | `example.com/about`          |
| Korean   | `example.com/소개`           |
| Chinese  | `example.com/介绍`           |
| Japanese | `example.com/紹介`           |
| Spanish  | `example.com/sobre-nosotros` |
| French   | `example.com/a-propos`       |

**Key Differences between Astro Official Recipe**
| Aspect | Astro Official Recipe | This Project |
|-----------------------|--------------------------------------|-------------------------------------|
| Default language | At root, romanized/English slugs | At root, native Korean slugs |
| Other languages | In subfolders (e.g., /en/, /fr/) | In /en/ subfolder |
| Slug style | English/romanized | Native language (Korean) |
| Navigation | English/romanized | Native for Korean, English for /en|
| Language switcher | Simple path swap | Path mapping, supports native slugs |
| Dynamic routes | English/romanized | Native for Korean, English for /en|

**Why Is this better?**

- User Experience:
  This approach is more user-friendly for native speakers, as URLs are in their native language.
- SEO:
  Native slugs can improve SEO for Korean search terms.
- Customization:
  I wanted a truly bilingual site with native experience for both languages, not just a translation of English slugs.
- Astro Flexibility:
  Astro’s file-based routing allows for this flexibility, even though the official recipe uses romanized slugs for simplicity and universality.

**Summary Table of Implementation**
| Feature | Korean (default) | English (secondary) |
|------------------------|-------------------------|--------------------------|
| Main pages | Native slugs (e.g., /홈) | /en/ subfolder |
| Blog posts | /글/글-x.md | /en/posts/post-x.md |
| Tag pages | /태그/인덱스, /태그/[tag] | /en/tags, /en/tags/[tag] |
| Navigation | Korean links | English links |
| Language switcher | Mapping logic | Mapping logic |
| Layouts/components | Shared | Shared |
| SEO/lang attribute | Dynamic | Dynamic |

**DEMO: https://astro-tutorial-i11n.vercel.app/en/**
