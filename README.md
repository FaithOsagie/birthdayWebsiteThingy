# 🎂 Birthday Website Template

A free, customisable birthday website you can make your own. Built with plain HTML, CSS and JavaScript, with no frameworks, no build step and no dependencies. It opens with an envelope landing page, then leads into a full-screen, scroll-snapping story with music, confetti, a typewriter message, a scratch card and a photo timeline.

Fork it, swap in your own name, photos and messages, and send the link to someone you love.

## ✨ Features

- **Envelope landing page** (`index.html`): ripple effect on click, zoom-out transition, and wording that switches to "Tap to open…" on touch devices.
- **Full-screen snap-scroll sections** that fade in and animate their children with staggered delays, using an `IntersectionObserver`.
- **Background music** with a Mute/Unmute button and an animated equaliser bar. Autoplay is attempted on load and retried on the first click, since browsers often block it.
- **Typewriter message** that types a note, a signature and a P.S. when the section first scrolls into view.
- **Confetti engine** on a canvas: a burst on load, a big burst on the finale, a "Celebrate again!" button, and a burst when the scratch card is revealed.
- **Scratch card** (mouse and touch) that reveals a hidden message once about 55% is scratched away.
- **Navigation dots** on the side that highlight the current section and jump to any section on click.
- Falling flower petals in the hero, a custom 🌸 cursor, and a responsive layout for mobile.

## 📁 Project Structure

```
.
├── index.html        # Envelope landing page (styles are inline)
├── birthday.html     # Main birthday experience
├── style.css         # Styles for birthday.html
├── script.js         # Behaviour for birthday.html
├── images/           # Your photos (not included, add your own)
│   ├── babyFriend.jpg
│   ├── schoolFriend.jpg
│   ├── adventureFriend.jpg
│   ├── glowUpFriend.jpg
│   └── bestFriend.jpg
└── your-song.mp3     # Your music (not included, add your own)
```

> **Photos and music are not included.** Image slots are intentionally left empty, and the music file is not bundled because songs are copyrighted. Add your own files before you share your version.

## 🚀 Getting Started

1. Clone or download this repo.

   ```bash
   git clone https://github.com/<your-username>/birthdayWebsiteThingy.git
   cd birthdayWebsiteThingy
   ```

2. Add your photos to an `images/` folder and an `.mp3` next to `birthday.html`.
3. Open `index.html` in a browser. Clicking the card takes you to `birthday.html`.
4. Or run a local server:

   ```bash
   python3 -m http.server 8000
   # then visit http://localhost:8000
   ```

An internet connection is needed for the Google Fonts (Great Vibes, DM Sans, Playfair Display). The page falls back to system fonts if they fail to load.

## 🧩 Page Sections

| # | Section ID  | What it does                                       |
|---|-------------|----------------------------------------------------|
| 1 | `#hero`     | Greeting, animated heading and falling petals      |
| 2 | `#message`  | Typewriter love note, signature and P.S.           |
| 3 | `#gallery`  | "Favourite Moments" photo grid with captions       |
| 4 | `#funfacts` | "Reasons we love…" alternating photo and text rows |
| 5 | `#surprise` | Scratch-to-reveal card                             |
| 6 | `#wishes`   | Wish cards from friends                            |
| 7 | `#timeline` | Milestones with photos                             |
| 8 | `#finale`   | Closing message, confetti and replay button        |

The section IDs are listed in `SECTION_IDS` in `script.js`. If you add, remove or rename a section, update that array and the nav dots in `birthday.html`.

## 🛠️ Make It Yours

### 1. Replace the name and text
- **Name:** the template uses **"Friend"** as a placeholder in `birthday.html`. Search for `Friend` and replace it with the birthday person's name. Also update the `<title>` tags and the heading text in `index.html`.
- **Typewriter note:** edit `TYPEWRITER_TEXT`, `TYPEWRITER_SIG` and `TYPEWRITER_END` at the top of `script.js`.
- **Reasons, captions and wishes:** these hold Lorem ipsum placeholder text in `birthday.html`. Replace them with real messages.
- **Wish cards:** copy a `.wish-card` block to add one. Initials go in `.wish-avatar` and the sender's name in `.wish-name`.
- **Scratch-card message:** edit the `.reveal-msg` block in the `#surprise` section.
- **Date line:** the hero eyebrow text (`To the Queen and owner of May 21ST`) and the timeline's "May 21st" entry are examples, so change them to the real date.

### 2. Add your media
- **Gallery and "reasons" photos:** the `<img src="">` tags are empty. Add paths such as `./images/photo1.jpg`, and write a short `alt` description for each.
- **Timeline photos:** drop images into `images/` using the file names above, or change the `src` paths.
- **Music:** point the `<source>` inside `<audio id="bg-music">` at your own `.mp3`. Use a track you have the rights to (for example, one with a CC0 or Creative Commons licence) and credit the artist if the licence requires it.

### 3. Change the look
- **Colours:** change the CSS variables in `:root` at the top of `style.css` (`--peach`, `--brown`, `--cream` and so on).
- **Confetti colours:** edit the `COLORS` array in `script.js`.
- **Typewriter speed:** adjust the `speed` variable (ms per character) in `script.js`.
- **Scratch difficulty:** the reveal threshold is `0.55` and the brush radius is `30`, both in the scratch card code.

## 🌐 Browser Support

Works in current versions of Chrome, Edge, Firefox and Safari. It relies on CSS scroll-snap, `IntersectionObserver` and the Canvas API. Browsers often block autoplay until the first tap or click, so the music may not start straight away.

## 🚢 Deployment

It is a static site, so it can be hosted on GitHub Pages, Netlify, Vercel or any static host. Upload every file, including `images/` and your audio file, keeping `index.html` at the root.

## 🤝 Contributing

Contributions are welcome. Bug fixes, new sections, new colour themes and accessibility improvements are all appreciated.

1. Fork the repo
2. Create a branch (`git checkout -b feature/my-idea`)
3. Commit your changes
4. Open a pull request

## 💌 Credits

Created by Osagie Faith. If you use this template, a star ⭐ on the repo is always appreciated.