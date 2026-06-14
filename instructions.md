# **Free Games Directory**

## **Context**

Free Games Directory is a web-based game discovery platform that allows visitors to browse free games and access official download sources.

The platform acts as a curated directory of free games across multiple genres. Users can browse featured games, search for titles, filter games by genre, view detailed information, and access official download pages.

This project is intentionally limited to a frontend-only implementation. All game information is stored locally in a JSON file. No backend services, databases, authentication systems, payment systems, user-generated content, or file hosting functionality are included.

The objective is to create a game discovery website that can be deployed as a static React application while maintaining a limited development scope suitable for a small-budget MVP.

---

## **Budget Tier**

**$150–$200**

---

## **Expected Timeline**

**5–7 Calendar Days**

---

## **Main Goal**

Build a React-based website that allows users to:

* Browse featured games  
* Search games by title  
* Filter games by genre  
* View detailed game information  
* Access official download sources

The website must operate entirely on the frontend without requiring backend infrastructure.

---

## **Style Guide**

#### Colors

| Use | Hex |
|---|---|
| Page background | `#111111` |
| Card background | `#1e1e1e` |
| Primary accent (CTAs, active states, links on hover) | `#00ff88` |
| Primary text | `#ffffff` |
| Secondary text (descriptions, labels) | `#aaaaaa` |
| Borders / dividers | `#2a2a2a` |

No gradients, no glow/shadow effects, no light or white backgrounds anywhere.

#### Genre Badge Colors

| Genre | Background | Text (on badge) |
|---|---|---|
| Action | `#ef4444` | `#4a1313` |
| Puzzle | `#3b82f6` | `#0c2c53` |
| RPG | `#8b5cf6` | `#26215c` |
| Arcade | `#eab308` | `#412402` |
| Adventure | `#22c55e` | `#173404` |
| Strategy | `#f97316` | `#4a1b0c` |

Badges: small, rounded (pill shape), semi-bold text, uppercase.

#### Typography

| Element | Style |
|---|---|
| Headings | Bold, sans-serif (Inter or system font) |
| Body text | Regular weight, `#aaaaaa` on dark background |
| Buttons | Bold, uppercase, letter-spacing ~0.5px |
| Genre badges | Small (11-12px), rounded, semi-bold, uppercase |

#### Layout

- Max content width: `1200px`, centered.
- Grid: 4 columns desktop (1200px+), 2 columns tablet (768px), 1 column mobile (480px).
- Hover effects: subtle scale (~1.02-1.03x) or border color change to `#00ff88`. Nothing else.

#### Components

**Buttons**

- **Primary CTA** (e.g. "Browse Games"): solid `#00ff88` background, `#111111` text, bold uppercase.
- **View Game / outline button**: transparent background, `#00ff88` border and text; on hover, fills solid `#00ff88` with `#111111` text.
- **Genre filter buttons**: `#1e1e1e` background, `#2a2a2a` border by default; active state is solid `#00ff88` with `#111111` text.

**Game Card**

Each card contains:
- Screenshot (16:9-ish crop, object-fit: cover, falls back to a placeholder if the image fails)
- Title (bold, white)
- Genre badge + platform tag (side by side)
- "View Game" button (full width)

Card styles:
- `width: 280px`, `background: #1e1e1e`, `border: 1px solid #2a2a2a`, `border-radius: 4px`
- On hover / focus-within: `transform: scale(1.02)`, `border-color: #00ff88`, transition `0.15s ease`
- Screenshot height: `140px`, `object-fit: cover`; background `#2a2a2a` as placeholder
- Title: `font-size: 16px`, `font-weight: 700`, color `#ffffff`
- Badge: `font-size: 11px`, `font-weight: 600`, `text-transform: uppercase`, `letter-spacing: 0.5px`, `padding: 4px 10px`, `border-radius: 12px`
- Platform tag: `background: #2a2a2a`, `color: #aaaaaa`
- "View Game" button: `display: block`, full width, `background: transparent`, `border: 1px solid #00ff88`, `color: #00ff88`, bold uppercase, `font-size: 12px`, `padding: 10px`, `border-radius: 4px`; on hover fills `#00ff88` with `#111111` text

**Navbar**

- Sticky, `#111111` background, bottom border `#2a2a2a`.
- Logo on the left, nav links on the right.
- Below 768px: collapse links into a hamburger menu.

### **Reference Materials**

### **1\. Reference Image**

Provided reference image is the logo design that must be used for:

* Navbar branding  
* Browser favicon (if applicable)

---

## **Requirements**

### **Core Features**

* Homepage displaying featured games  
* Browse page displaying all games  
* Search functionality  
* Genre filtering  
* Game detail page  
* Official download links  
* Responsive layout for desktop, tablet, and mobile devices

---

## **Technology Requirements**

### **Frontend**

* React.js  
* React Router DOM v6
* Tailwind CSS  
* JavaScript (ES6+)

### **Data Source**

* Local JSON file

### **Deployment**

* Vercel

### **Version Control**

* GitHub

---

## **Data Requirements**

All game data must be loaded from:

```
src/data/games.json
```

The JSON file acts as the single source of truth for all game content.

The developer is responsible for creating and populating the games.json.
Each game entry must contain:

```json
{
  "id": 1,
  "title": "Game Title",
  "genre": "Action",
  "platform": "Windows",
  "description": "Game description",
  "imageUrl": "https://...",
  "downloadUrl": "https://...",
  "featured": true
}
```

### **Minimum Content Requirements**

* Minimum 10 game entries  
* Minimum 6 featured games  
* All image URLs must display successfully  
* All download links must point to official sources  
* Display a placeholder image if an image fails to load

---

## **Routing Requirements**

The application must contain exactly three routes.

### **Home Page**

Route:

```
/
```

### **Browse Page**

Route:

```
/browse
```

### **Game Detail Page**

Route:

```
/game/:id
```

No additional routes are required.

---

## **Home Page Requirements**

### **Navbar**

Display:

* Website logo  
* Website name  
* Home navigation link  
* Browse navigation link

### **Hero Section**

Heading:

```
Discover & Download Free Games
```

Primary Button:

```
Browse Games
```

The button must navigate to:

```
/browse
```

### **Genre Categories**

Display the following categories:

* Action  
* Puzzle  
* RPG  
* Arcade  
* Adventure  
* Strategy

Selecting a category must open the Browse page with the selected genre active.

### **Featured Games Section**

Display six featured games.

Each game card must contain:

* Screenshot  
* Game title  
* Genre badge  
* Platform tag  
* View Game button

### **Footer**

Display:

* Website name  
* Copyright notice  
* Home link  
* Browse link

---

## **Browse Page Requirements**

### **Search**

Display a search field with the placeholder:

```
Search games...
```

Behavior:

* Filter games while the user types  
* Search against game titles only  
* No API requests

### **Genre Filters**

Display the following options:

* All  
* Action  
* Puzzle  
* RPG  
* Arcade  
* Adventure  
* Strategy

Requirements:

* All selected by default  
* Active filter visually distinct  
* Search and genre filters operate together

### **Games Grid**

Display all games in a responsive grid.

| Device | Columns |
| ----- | ----- |
| Desktop | 4 |
| Tablet | 2 |
| Mobile | 1 |

If no results match:

```
No games found
```

must be displayed.

---

## **Game Detail Page Requirements**

Route:

```
/game/:id
```

Display:

* Back button  
* Game title  
* Screenshot  
* Genre badge  
* Platform tag  
* Description  
* Download button

### **Download Button Requirements**

* Open in a new browser tab  
* Link to the official game source  
* Link must not point to unofficial mirrors

---

## **Folder Structure**

```
free-games-directory/
│
├── public/
│   └── index.html
│
├── src/
│   ├── data/
│   │   └── games.json
│   ├── pages/
│   │   ├── Home.jsx
│   │   ├── Browse.jsx
│   │   └── GameDetail.jsx
│   ├── components/
│   │   ├── Navbar.jsx
│   │   ├── GameCard.jsx
│   │   ├── GenreFilter.jsx
│   │   └── Footer.jsx
│   ├── App.jsx
│   ├── index.js
│   └── index.css
│
├── package.json
└── README.md
```

---

## **Deliverables**

| \# | Deliverable | Format | Quantity | Specification |
| ----- | ----- | ----- | ----- | ----- |
| 1 | Application Source Code | React source files (.jsx, .js, .css, .json) | 1 complete project | Must match the specified folder structure |
| 2 | GitHub Repository | Public URL | 1 | Contains complete project source code |
| 3 | Live Website | Vercel URL | 1 | Public deployment |
| 4 | Game Data File | JSON | 1 file | Minimum 10 game entries |
| 5 | Project Documentation | README.md | 1 file | Setup instructions and game data editing instructions |

---

## **Scope Boundaries**

The following items are not included:

* User accounts  
* Authentication systems  
* Firebase  
* Supabase  
* Databases  
* Backend APIs  
* Comments  
* Reviews  
* Ratings  
* User submissions  
* File uploads  
* File hosting  
* Payment processing  
* Admin dashboard  
* Multiplayer functionality  
* Chat functionality  
* Notification systems  
* External game APIs

---

## **Quality Control Checklist**

Before submission verify the following:

* Home page loads correctly  
* Browse page loads correctly  
* Game Detail page loads correctly  
* Search functionality operates correctly  
* Genre filtering operates correctly  
* Six featured games appear on the Home page  
* Download links open in a new browser tab  
* No browser console errors are present  
* No broken images are displayed

---

## **Acceptance Checklist**

The project is complete only if all of the following conditions are met:

* All content loads from `games.json`  
* Folder structure matches specification  
* GitHub repository is public  
* Vercel deployment is public  
* Deliverables are provided

---

## **Final Goal**

The completed website must allow visitors to browse featured games, search titles, filter games by genre, view game information, and access official download sources through a React-based frontend application that loads all content from a local JSON file and matches the requirements defined in this document.

