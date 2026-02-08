# 📚 Shelf - Book Recommender App

A beautiful, minimalist book discovery app with Bauhaus-inspired design. Discover your next great read from a curated collection of 200+ books across multiple genres.

![PWA Ready](https://img.shields.io/badge/PWA-ready-blue.svg)
![Books](https://img.shields.io/badge/books-200+-success.svg)
![Offline](https://img.shields.io/badge/offline-support-orange.svg)

## ✨ Features

### 🎲 Random Book Generator
- Instant book recommendations at the click of a button
- Filter by category (All, Fiction, Nonfiction, Philosophy, Women Writers)
- Never run out of reading ideas

### 📅 Daily Editor's Picks
- 5 curated books refreshed every day
- Smart shuffling algorithm ensures variety
- Filter by genre to discover specific categories
- Never see the same picks two days in a row

### 📖 Personal Reading List
- Add any book with one click
- Track your reading progress with completion checkboxes
- Remove finished books or clear all completed at once
- Persistent across sessions (saved in browser)
- Add custom books not in the database

### 🎨 Beautiful Bauhaus Design
- Bold primary colors (Red, Blue, Yellow)
- Geometric patterns and shapes
- Clean, modernist typography
- High contrast for excellent readability
- Mobile-first responsive design

### 📴 Full PWA Support
- Works completely offline
- Installable on mobile and desktop
- Fast loading with service worker caching
- Runs in standalone app mode

## 📚 Book Collection

### 200+ Curated Books Including:

**Fiction (90+ books)**
- Modern Bestsellers: The Midnight Library, Project Hail Mary, The Night Circus
- Literary Classics: 1984, The Great Gatsby, To Kill a Mockingbird
- International Fiction: 1Q84 (Murakami), One Hundred Years of Solitude (García Márquez)
- Sci-Fi Classics: Dune, Foundation, Neuromancer, Hyperion
- Mystery & Thriller: The Silent Patient, Gone Girl, Big Little Lies

**Nonfiction (50+ books)**
- History: Sapiens, Guns Germs and Steel, The Anarchy
- Memoirs: Educated, Born a Crime, When Breath Becomes Air
- Science: A Short History of Nearly Everything, The Gene
- Self-Improvement: Atomic Habits, Thinking Fast and Slow
- Indian History: City of Djinns, Inglorious Empire, Maximum City

**Philosophy (45+ books)**
- Eastern Philosophy: I Am That, Bhagavad Gita commentaries, Upanishads
- Existentialism: Being and Nothingness, The Myth of Sisyphus, Nausea
- Stoicism: Meditations (Marcus Aurelius), Letters from a Stoic
- Modern Philosophy: Justice (Sandel), The Problems of Philosophy
- Spiritual Teachers: Krishnamurti, Osho, Ramana Maharshi

**Women Writers (29+ books)**
- Margaret Atwood: The Handmaid's Tale, Alias Grace, The Testaments
- Virginia Woolf: Mrs Dalloway, To the Lighthouse, Orlando, The Waves
- Clarice Lispector: The Hour of the Star, Água Viva, Near to the Wild Heart
- Ursula K. Le Guin: The Left Hand of Darkness, The Dispossessed
- Octavia Butler: Kindred, Parable of the Sower
- Sylvia Plath: The Bell Jar, Ariel, Collected Poems
- Agatha Christie: Murder on the Orient Express, Death on the Nile

## 🎯 How to Use

### Discover Books

1. **Random Generator**
   - Select a category (or choose "All Books")
   - Click "🎲 Get Random Book"
   - Get instant recommendations
   - Click again for a different book

2. **Editor's Picks**
   - Scroll to see 5 daily curated books
   - Filter by Fiction, Nonfiction, Philosophy, or Women Writers
   - New picks shuffle every day at midnight

3. **Reading List**
   - Click "+ Add to List" on any book
   - Books appear in your personal reading list
   - Check the box when you finish reading
   - Click "Clear Completed" to remove finished books

4. **Add Custom Books**
   - Can't find a book in the database?
   - Use the "Add Custom Book" form
   - Enter title and author
   - Instantly added to your reading list

## 🎨 Design Details

### Color Palette
Inspired by Bauhaus design movement:

```css
Primary Red:    #D92B2B  /* Vibrant, geometric accent */
Deep Blue:      #1E5B9E  /* Strong, stable contrast */
Golden Yellow:  #F1B422  /* Warm, energetic highlights */
Charcoal Black: #1A1A1A  /* Bold structure and text */
Cream:          #E8E4D9  /* Soft, neutral background */
Teal Blue:      #3E7E8E  /* Secondary accent */
```

### Typography
- **Headings**: Crimson Pro (serif, elegant)
- **Body**: DM Sans (sans-serif, clean)
- **Accent**: Uppercase labels with letter-spacing

### Design Principles
- Angular cards with bold 3px borders (no rounded corners)
- Geometric background patterns
- High contrast color blocking
- Flat design with strategic shadows
- Mobile-first responsive layout

## 💾 Data & Privacy

### Data Storage
- All data stored locally in browser's `localStorage`
- No server, no database, no cloud storage
- Your reading list stays on your device

### What's Stored
- Your personal reading list
- Completion status of books
- Today's shuffled Editor's Picks (refreshes daily)

### Privacy
- ✅ No tracking scripts
- ✅ No analytics
- ✅ No cookies
- ✅ No personal data collection
- ✅ 100% offline-capable

### Data Persistence
- Reading list persists across browser sessions
- Survives page refreshes
- ⚠️ Clearing browser data will delete your reading list
- Each browser has its own separate data

## 🛠️ Technical Details

### Built With
- **HTML5** - Semantic markup
- **CSS3** - Custom properties, Grid, Flexbox
- **Vanilla JavaScript** - No frameworks or libraries
- **Service Worker** - Offline support and caching
- **Web App Manifest** - PWA metadata

### Browser Support
- ✅ Chrome/Edge (90+)
- ✅ Firefox (88+)
- ✅ Safari (14+)
- ✅ Mobile browsers (iOS Safari, Chrome Android)

### File Structure
```
book-recommender.html    # Main app file (complete standalone)
book-sw.js              # Service worker for offline support
book-manifest.json      # PWA manifest with app metadata
icons/                  # App icons (need to be created)
  book-icon-72.png
  book-icon-96.png
  book-icon-128.png
  book-icon-144.png
  book-icon-152.png
  book-icon-192.png
  book-icon-384.png
  book-icon-512.png
```

### Database Structure
Books are stored as JavaScript objects:
```javascript
{
  title: "Book Title",
  author: "Author Name",
  snippet: "Compelling one-sentence description",
  badge: "Fiction" // or Nonfiction, Philosophy, Women Writers
}
```

### Features Implementation
- **Daily Shuffle**: Uses `Date.toDateString()` to reset picks daily
- **Random Generator**: `Math.random()` for instant recommendations
- **Reading List**: `localStorage` with JSON serialization
- **Filters**: Array filtering by badge property
- **PWA**: Service worker caches all assets for offline use

## 🔧 Customization

### Add Books to Database

Open `book-recommender.html` and find the `completeBookDatabase` array:

```javascript
const completeBookDatabase = [
  // ... existing books ...
  
  // Add your book here:
  { 
    title: "Your Book Title", 
    author: "Author Name", 
    snippet: "A compelling one-sentence description.", 
    badge: "Fiction" // or "Nonfiction", "Philosophy", "Women Writers"
  },
];
```

### Change Colors

Edit CSS variables in the `<style>` section:

```css
:root {
  --bauhaus-red: #D92B2B;    /* Change primary red */
  --bauhaus-blue: #1E5B9E;   /* Change blue accent */
  --bauhaus-yellow: #F1B422; /* Change yellow highlight */
  --bauhaus-black: #1A1A1A;  /* Change text color */
  --bauhaus-cream: #E8E4D9;  /* Change background */
}
```

### Modify Fonts

Change Google Fonts import in `<head>`:

```html
<link href="https://fonts.googleapis.com/css2?family=Your+Font&display=swap" rel="stylesheet">
```

Then update CSS:
```css
h1 { font-family: 'Your Font', serif; }
body { font-family: 'Your Font', sans-serif; }
```

### Adjust Number of Editor's Picks

Find the `renderEditorsPicks()` function:
```javascript
const booksToShow = filteredPicks.slice(0, 5); // Change 5 to any number
```

## 📱 Installation

### As PWA (Recommended)

**On Mobile:**
1. Open the app in browser (Chrome, Safari)
2. Tap "Add to Home Screen" when prompted
3. App installs like a native app
4. Launch from home screen icon

**On Desktop:**
1. Open in Chrome/Edge
2. Look for install icon in address bar
3. Click to install
4. App appears in applications folder

### In Browser
Simply open `book-recommender.html` in any modern browser!

## 🚀 Deployment

### Quick Deploy

**Vercel (Recommended):**
1. Push to GitHub
2. Import to Vercel
3. Deploy in 30 seconds
4. Get HTTPS URL automatically

**Netlify:**
1. Drag & drop file to Netlify
2. Get instant deployment
3. Free SSL included

**GitHub Pages:**
1. Enable Pages in repo settings
2. Select main branch
3. Get `username.github.io/repo-name` URL

### Requirements
- Must be served over HTTPS for PWA features
- Icons needed for app installation
- Service worker needs proper MIME types

## 🐛 Troubleshooting

**Books not appearing?**
- Check browser console for JavaScript errors
- Ensure `completeBookDatabase` is properly formatted
- Verify no syntax errors in book objects

**Reading list not saving?**
- Check if localStorage is enabled
- Verify you're not in private/incognito mode
- Check browser storage quota

**Daily picks not changing?**
- Picks change at midnight local time
- Clear localStorage to force refresh
- Check `dailyPicksDate` in browser DevTools

**PWA not installing?**
- Ensure you're on HTTPS (not `file://`)
- Create and upload all icon sizes
- Check manifest.json is loading correctly
- Look for errors in browser console

**Service worker errors?**
- Normal in local development (needs HTTPS)
- Works fine once deployed to server
- Can comment out SW registration for local testing

## 🎯 Use Cases

### For Readers
- Discover new books across genres
- Track your reading progress
- Get daily curated recommendations
- Never forget what you want to read

### For Book Clubs
- Share the app link with members
- Everyone can browse the same collection
- Add custom books for club selections

### For Students
- Track reading assignments
- Discover philosophy and classics
- Organize research reading

### For Personal Growth
- Explore spiritual and philosophy texts
- Track self-improvement books
- Get recommendations across topics

## 📊 Statistics

- **Total Books**: 200+
- **Categories**: 4 (Fiction, Nonfiction, Philosophy, Women Writers)
- **Daily Picks**: 5 books
- **File Size**: ~150KB (including all books!)
- **Load Time**: <1 second (after first load)
- **Offline**: 100% functional

## 🎁 Future Features (Ideas)

- [ ] Search functionality
- [ ] Filter by author
- [ ] Reading goals and stats
- [ ] Book notes/reviews
- [ ] Export reading list to text/CSV
- [ ] Dark mode toggle
- [ ] Goodreads integration
- [ ] ISBN lookup for book details
- [ ] "Already read" vs "To read" lists
- [ ] Recommendations based on reading history

## 📜 License

Free for personal use. No attribution required.

## 🙏 Credits

**Inspired By:**
- Bauhaus design movement (1919-1933)
- Modernist typography and geometric abstraction
- Swiss design principles

**Books Curated From:**
- Personal reading recommendations
- Literary classics and bestsellers
- Contemporary fiction and nonfiction
- Philosophy and spiritual texts

**Built With Love Using:**
- Pure vanilla JavaScript (no frameworks!)
- Modern CSS (Grid, Flexbox, Custom Properties)
- Progressive Web App APIs
- localStorage for data persistence

---

## 📚 Book Recommendations by Category

### Best Starting Points

**If you're new to:**
- **Fiction**: The Midnight Library, The Night Circus, Project Hail Mary
- **Nonfiction**: Sapiens, Educated, Atomic Habits
- **Philosophy**: Man's Search for Meaning, Meditations, The Myth of Sisyphus
- **Women Writers**: The Handmaid's Tale, The Bell Jar, To Kill a Mockingbird

### Most Popular
1. The Midnight Library - Matt Haig
2. Atomic Habits - James Clear
3. The Silent Patient - Alex Michaelides
4. Sapiens - Yuval Noah Harari
5. 1984 - George Orwell

### Hidden Gems
- Drive Your Plow Over the Bones of the Dead - Olga Tokarczuk
- The Passion According to G.H. - Clarice Lispector
- The Dispossessed - Ursula K. Le Guin
- I Am That - Nisargadatta Maharaj
- The Vegetarian - Han Kang

---

**⭐ Enjoy discovering your next great read!**

**💬 Questions?** Check the main project README or deployment guides.

**🚀 Ready to deploy?** See `DEPLOYMENT-GUIDE.md` in the root folder.
