# Booksmap - Multi-Book Mind Map Collection

## Project Overview

Booksmap is a static HTML website collection presenting various books in an accessible, mind-map style format. Each book gets its own directory with a consistent structure and shared styling.

## Project Structure

```
booksmap/
├── CLAUDE.md                        # This file - shared guidelines
├── index.html                       # Main homepage with all books
├── shared/
│   ├── styles.css                   # Common CSS for all books
│   └── highlight.js                 # Text highlighting feature
├── bhagavad-gita/
│   ├── index.html                   # Main landing page
│   ├── styles.css                   # Book-specific overrides (optional)
│   └── chapters/
│       └── chapter-XX.html          # Individual chapter pages
├── the-untethered-soul/
│   ├── index.html
│   ├── styles.css
│   └── chapters/
│       └── chapter-XX.html
└── [future-books]/
```

---

## How to Generate a New Mind Map

When asked to create a mind map for a book, follow these steps:

### Step 1: Research the Book Structure

Before creating files, understand the book's organization:
- Number of chapters/parts/sections
- Chapter titles and themes
- Key concepts and teachings
- The book's central message

### Step 2: Create Directory Structure

```bash
mkdir -p booksmap/[book-name]/chapters
```

Use kebab-case for directory names (e.g., `the-untethered-soul`, `psychology-of-money`).

### Step 3: Choose a Color Theme

Select an accent color that fits the book's theme:
- Spirituality/Consciousness: Violet/Purple (#7c3aed)
- Finance/Money: Green (#059669)
- Philosophy/Stoicism: Blue-Purple (#667eea)
- Parenting/Relationships: Teal (#0891b2)
- Technology/AI: Blue (#3b82f6)
- Creativity/Content: Orange (#f97316)
- Religion/Sacred texts: Saffron (#ff6b35)

### Step 4: Create Book-Specific Styles (styles.css)

Create `[book-name]/styles.css` with CSS custom properties:

```css
/* [Book Name] - Book-Specific Styles */

:root {
    --accent-color: #XXXXXX;
    --accent-color-dark: #XXXXXX;
    --accent-gradient: linear-gradient(135deg, #XXXXXX 0%, #XXXXXX 100%);
    --section-title-bg: #XXXXXX;
    --key-box-color: #XXXXXX;
    --key-box-bg: #XXXXXX;
    --verse-bg: #XXXXXX;
    --intro-bg: #XXXXXX;
}

/* Add book-specific classes as needed */
```

#### Common Book-Specific Classes to Consider

Depending on the book type, add relevant classes:

**For spiritual/philosophical books:**
```css
.insight-box { }      /* Key spiritual insights */
.practice-box { }     /* Meditation/awareness exercises */
.quote-box { }        /* Notable quotes */
.metaphor-box { }     /* Key metaphors/analogies */
.reflection { }       /* Questions for contemplation */
.central-teaching { } /* Highlighted core message */
```

**For practical/how-to books:**
```css
.technique { }        /* Specific techniques */
.example-dialogue { } /* Conversation examples */
.skill-box { }        /* Step-by-step skills */
.common-mistake { }   /* What to avoid */
.success-story { }    /* Positive examples */
.quick-reference { }  /* Summary cards */
```

### Step 5: Create the Main Index Page (index.html)

The index page should include:

1. **Header Section**
   - Book title (h1)
   - Subtitle with author
   - Introduction box explaining the mind map

2. **Central Node**
   - Book's main title/concept
   - Optional tagline or core message

3. **Sections for Each Part/Theme**
   - Section title bar
   - Chapters grid with chapter cards
   - Each card: chapter number, name, description, stats

4. **Key Teachings Summary**
   - Bullet points of core lessons

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[Book Title] Mind Map</title>
    <link rel="stylesheet" href="../shared/styles.css">
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>[Book Title]</h1>
        <div class="subtitle">[Subtitle] by [Author]</div>

        <div class="intro">
            <h2>About This Mind Map</h2>
            <p>[Description of what the book covers and how this mind map presents it]</p>
        </div>

        <div class="central-node">
            [BOOK TITLE]<br>
            <span style="font-size: 0.6em; font-weight: normal;">[Core message or tagline]</span>
        </div>

        <div class="mindmap">
            <div class="section">
                <div class="section-title">PART/SECTION NAME</div>
                <div class="chapters-grid">
                    <a href="chapters/chapter-01.html" class="chapter-card">
                        <span class="chapter-number">Chapter 1</span>
                        <div class="chapter-name">[Chapter Title]</div>
                        <div class="chapter-description">[2-3 sentence description]</div>
                        <div class="concept-count">[X] Key Concepts</div>
                    </a>
                    <!-- More chapter cards -->
                </div>
            </div>
            <!-- More sections -->
        </div>

        <div class="key-teachings">
            <h3>Core Teachings of [Book Title]</h3>
            <ul>
                <li><strong>[Concept]</strong> — [Brief explanation]</li>
                <!-- More key teachings -->
            </ul>
        </div>
    </div>
    <script src="../shared/highlight.js" defer></script>
</body>
</html>
```

### Step 6: Create Chapter Pages

For each chapter, create `chapters/chapter-XX.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chapter X: [Title] - [Book Name]</title>
    <link rel="stylesheet" href="../../shared/styles.css">
    <link rel="stylesheet" href="../styles.css">
</head>
<body>
    <div class="container container-narrow">
        <a href="../index.html" class="back-button">← Back to Mind Map</a>

        <h1 class="chapter-title">Chapter X: [Title]</h1>
        <div class="chapter-meta">[Part Name or Subtitle]</div>

        <div class="intro">
            <p>[Chapter introduction - what this chapter covers]</p>
        </div>

        <div class="section">
            <h2>[Section Title]</h2>
            <p>[Explanatory content - make it accessible and engaging]</p>

            <div class="quote-box">
                "[Notable quote from the book]"
                <div class="attribution">— [Author]</div>
            </div>
        </div>

        <div class="section">
            <h2>[Another Section]</h2>
            <p>[More content]</p>

            <div class="insight-box">
                <h4>Key Insight</h4>
                <p>[Important takeaway]</p>
            </div>

            <div class="metaphor-box">
                <h4>[Metaphor Name]</h4>
                <p>[Explanation of the metaphor]</p>
            </div>
        </div>

        <div class="practice-box">
            <h4>Practice: [Practice Name]</h4>
            <ol>
                <li>[Step 1]</li>
                <li>[Step 2]</li>
                <!-- More steps -->
            </ol>
        </div>

        <div class="key-points">
            <h3>Key Takeaways</h3>
            <ul>
                <li>[Takeaway 1]</li>
                <li>[Takeaway 2]</li>
                <!-- More takeaways -->
            </ul>
        </div>

        <div class="chapter-nav">
            <a href="chapter-XX.html">← Previous: [Previous Chapter]</a>
            <a href="chapter-XX.html">Next: [Next Chapter] →</a>
        </div>
    </div>
    <script src="../../shared/highlight.js" defer></script>
</body>
</html>
```

### Step 7: Update the Main Homepage (index.html)

Add the new book to the root `index.html`:

1. **Add book cover style** in the `<style>` section:
```css
.book-cover.[book-class] {
    background: linear-gradient(135deg, #XXXXXX 0%, #XXXXXX 100%);
}
```

2. **Add book card** in the `#bookGrid` div:
```html
<a href="[book-name]/index.html" class="book-card"
   data-title="[Book Title]"
   data-author="[Author Name]"
   data-tags="[space-separated tags for filtering]">
    <div class="book-cover [book-class]">&#XXXXX;</div>
    <div class="book-title">[Book Title]</div>
    <div class="book-author">by [Author]</div>
    <div class="book-description">[2-3 sentence description]</div>
    <div class="book-stats">[X] Chapters | [Additional info]</div>
    <div class="book-tags">
        <span class="book-tag">[Tag 1]</span>
        <span class="book-tag">[Tag 2]</span>
        <span class="book-tag">[Tag 3]</span>
    </div>
</a>
```

#### Unicode Icons for Book Covers
- &#2384; (ॐ) - Spirituality/Hinduism
- &#9883; - Philosophy/Balance
- &#128430; - Technology/Networks
- &#9829; - Relationships/Love
- &#129504; - Brain/Psychology
- &#36; - Money/Finance
- &#127909; - Video/Content
- &#10024; (✨) - Consciousness/Soul
- &#128218; - Books/Learning

---

## Content Guidelines

### Writing Style
- Accessible to first-time readers while maintaining depth
- Explanatory prose sections between key content
- Practical applications and reflections
- Key insights as concise bullet points
- No unnecessary jargon
- Use the author's key metaphors and examples

### Content Organization
- Break complex ideas into digestible sections
- Use consistent heading hierarchy (h1 for title, h2 for sections, h3 for subsections)
- Include practical examples where relevant
- End chapters with key takeaways (4-6 bullet points)
- Include 1-2 notable quotes per chapter

### Chapter Content Depth
Each chapter should include:
- Introduction paragraph (what the chapter covers)
- 3-5 main sections with h2 headings
- At least one quote box with author attribution
- At least one insight/metaphor/practice box
- Key takeaways list at the end
- Proper navigation to previous/next chapters

---

## Shared Design System

### Color Palette
Each book can customize its accent color while maintaining the design system:
- **Primary accent:** Book-specific
- **Background gradient:** Purple (667eea to 764ba2)
- **Container background:** White
- **Text colors:** Dark gray (#2d3748, #4a5568)
- **Key points box:** Matches accent or teal (#38b2ac)

### Core CSS Classes
All books share these fundamental classes from `shared/styles.css`:
- `.container` / `.container-narrow` - Layout containers
- `.back-button` - Navigation back link
- `.intro` - Introduction box with left border
- `.central-node` - Main title node (customizable gradient)
- `.section` - Content sections
- `.section-title` - Section header bars
- `.chapters-grid` - Grid layout for chapter cards
- `.chapter-card` - Clickable chapter cards
- `.chapter-number`, `.chapter-name`, `.chapter-description` - Card contents
- `.key-points` / `.key-teachings` - Summary boxes
- `.chapter-nav` - Previous/Next navigation
- `.quote-box` - For notable quotes (if not in shared, add to book styles)
- `.verse` - For verses/quotes with special styling

---

## Technical Notes

- Pure HTML/CSS with vanilla JavaScript for highlighting
- No build tools or frameworks required
- Works offline once downloaded
- Print-friendly styling
- Accessible color contrast ratios
- localStorage used for highlight persistence (per-book storage keys)

## Highlight Feature

The shared `highlight.js` provides:
- Text selection and highlighting
- localStorage persistence
- Remove highlight functionality
- Works across all pages
- Storage key format: `[book]_highlights`

## Navigation Patterns

- Each chapter links to previous and next chapters
- First chapter: "Previous" links to overview
- Last chapter: "Next" links to overview
- All pages have "Back to Mind Map" link

---

## Checklist for New Mind Map

- [ ] Create directory: `[book-name]/`
- [ ] Create `[book-name]/chapters/` directory
- [ ] Create `[book-name]/styles.css` with theme colors
- [ ] Create `[book-name]/index.html` with all chapter cards
- [ ] Create all chapter files in `[book-name]/chapters/`
- [ ] Verify all chapter navigation links work
- [ ] Add book to root `index.html` homepage
- [ ] Add book cover CSS class to root `index.html`
- [ ] Test filtering/search on homepage includes new book
