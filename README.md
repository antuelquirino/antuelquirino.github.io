# antuelquirino.github.io

Personal portfolio, published by GitHub Pages from `main`:
https://antuelquirino.github.io

One static page (`index.html`, no build step) in English and Spanish.

## Adding a project

1. Put its media in `assets/`:
   - a demo video in `assets/video/` (MP4/H.264, 16:10, ideally ~30 s and ~1 MB), or a single image;
   - screenshots for the gallery in `assets/img/` (WebP, 1440×900 works well).
2. Add one object to the `PROJECTS` list in `index.html`. Copy an existing one; every field with
   `en` / `es` needs both languages:

   ```js
   {
     id: 'new-project',            // unique, no spaces
     featured: false,              // true = large card at the top
     title: 'New Project',
     kicker: { en: '…', es: '…' }, // featured only: the small line above the title
     desc: { en: '…', es: '…' },
     highlights: { en: ['…'], es: ['…'] },  // featured only, optional
     tags: ['Python', 'dbt'],
     url: 'new-project.vercel.app',          // shown in the browser bar
     video: 'assets/video/new-project-demo.mp4', poster: 'assets/img/new-project-1.webp',
     // or instead of video/poster: image: 'assets/img/new-project.png',
     links: [
       { kind: 'live', href: 'https://…' },  // live | app | api | tableau | github
       { kind: 'github', href: 'https://github.com/antuelquirino/…' }
     ],
     gallery: [
       { src: 'assets/img/new-project-1.webp', en: 'Caption', es: 'Leyenda' }
     ]
   }
   ```

3. Open the page locally (`python -m http.server` in this folder, then http://localhost:8000),
   check both languages and a phone-width window, and push.

Featured projects alternate sides automatically. A new link `kind` needs a label in
`LINK_LABELS`.

## Link preview

`assets/img/og.png` (1200×630) is the image LinkedIn, WhatsApp and Slack show when the link is
shared. If you change the headline, update it and the `og:` tags in `<head>` together.
