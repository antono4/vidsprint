# VidSprint - AI Short Video Finder for TikTok Content

## 1. Project Overview

**Project Name:** VidSprint  
**Type:** Web Application (AI-powered video search)  
**Core Functionality:** Aplikasi AI yang membantu kreator konten menemukan video short gratis untuk digunakan di TikTok dan platform sosial lainnya. Menggunakan **Pexels API** (free) untuk mencari dan mengunduh video berkualitas tinggi.  
**Target Users:** Content creators, TikTok enthusiasts, Social media managers

## API Integration

**Pexels API (Free)**
- Website: https://www.pexels.com/api/
- Free tier: 200 requests/hour, 10,000 requests/month
- Video quality: HD, 4K available
- License: Free for personal and commercial use

**API Key Configuration:**
- Replace `YOUR_PEXELS_API_KEY` in code with actual API key
- Get free API key at: https://www.pexels.com/api/

**Endpoints Used:**
- Search Videos: `GET /videos/search?query={query}&per_page=15`
- Popular Videos: `GET /videos/popular?per_page=15`

---

## 2. UI/UX Specification

### Layout Structure

**Page Sections:**
1. **Header** - Logo + Navigation minimal
2. **Hero Section** - Search bar dengan AI-powered suggestions
3. **Category Pills** - Quick filter untuk kategori populer
4. **Video Grid** - Responsive grid untuk hasil pencarian
5. **Video Modal** - Detail view dengan download option
6. **Footer** - Simple credits

**Layout:** Single page dengan modal untuk detail video  
**Responsive Breakpoints:**
- Mobile: < 640px (1 column)
- Tablet: 640px - 1024px (2 columns)
- Desktop: > 1024px (4 columns)

### Visual Design

**Color Palette:**
- Primary: `#6366F1` (Indigo vibrant)
- Secondary: `#EC4899` (Pink hot)
- Accent: `#F59E0B` (Amber energetic)
- Background: `#0F0F1A` (Dark deep)
- Surface: `#1A1A2E` (Card dark)
- Surface Light: `#252542` (Hover state)
- Text Primary: `#FFFFFF`
- Text Secondary: `#A0A0B8`
- Success: `#10B981`
- Gradient: linear-gradient(135deg, #6366F1 0%, #EC4899 100%)

**Typography:**
- Font Family: 'Plus Jakarta Sans' (Google Fonts)
- Headings: 700 weight
- Body: 400-500 weight
- Hero Title: 48px/56px
- Section Title: 32px
- Card Title: 18px
- Body Text: 14px-16px

**Spacing System:**
- Base unit: 8px
- Container padding: 24px
- Card gap: 16px
- Section gap: 48px

**Visual Effects:**
- Cards: 8px border-radius, subtle glow on hover
- Gradient text for highlights
- Glassmorphism effect on modal
- Smooth transitions (300ms ease)
- Floating animation on category pills

### Components

**1. Search Bar**
- Large input with gradient border
- Placeholder: "Cari video short untuk kontenmu..."
- Search icon (left)
- AI sparkle indicator
- States: default, focus (glow), loading

**2. Category Pills**
- Horizontal scrollable
- Categories: Trending, Lifestyle, Food, Travel, Fashion, Fitness, Comedy, Tech
- States: default, hover (scale + glow), active (filled)

**3. Video Card**
- Thumbnail preview (16:9 aspect ratio)
- Duration badge (bottom-left)
- Creator name (bottom-right)
- Hover: overlay dengan play icon + "Lihat Detail"
- Loading: skeleton placeholder

**4. Video Modal**
- Backdrop blur
- Video preview area
- Title, description, duration
- Download button (gradient)
- Source attribution (Pexels)
- Close button (top-right)

**5. No Results State**
- Illustration placeholder
- "Tidak ada video ditemukan"
- Suggestion untuk keyword lain

---

## 3. Functionality Specification

### Core Features

1. **AI-Powered Search**
   - Input pencarian dengan debounce (300ms)
   - Simulated AI enhancement untuk keyword suggestions
   - Tampilkan trending searches

2. **Category Filtering**
   - Filter cepat berdasarkan kategori
   - Kombinasi search + category

3. **Video Discovery**
   - Grid display dengan lazy loading
   - Infinite scroll simulation
   - Sort by relevance/newest

4. **Video Preview Modal**
   - Tampilkan video metadata
   - Simulasi download dengan progress
   - Link ke sumber asli (Pexels)

5. **Favorites/Collection**
   - Local storage untuk menyimpan video favorit
   - Quick access tab

### User Interactions & Flows

1. **Search Flow:**
   - User ketik keyword → Debounced search → Show loading → Display results
   - Empty search → Show popular/trending videos

2. **Category Flow:**
   - Click category pill → Filter videos → Update grid
   - Active category highlighted

3. **Video Detail Flow:**
   - Click video card → Open modal → Show details → Option to download/save

4. **Save Flow:**
   - Click heart icon → Save to localStorage → Update UI

### Data Handling

- Mock data untuk video results (simulasi API response)
- LocalStorage untuk favorites
- Simulasi loading states

### Edge Cases

- Empty search results → Show suggestions
- API error → Show retry option
- No favorites → Show empty state with CTA

---

## 4. Acceptance Criteria

### Visual Checkpoints

- [ ] Dark theme dengan gradient accents
- [ ] Smooth hover effects pada cards
- [ ] Responsive grid (1/2/4 columns)
- [ ] Gradient text pada logo/headings
- [ ] Glassmorphism modal effect
- [ ] Loading skeleton states
- [ ] Category pills dengan animation

### Functional Checkpoints

- [ ] Search bar berfungsi dengan debounce
- [ ] Category filter update results
- [ ] Video modal opens dengan data yang benar
- [ ] Favorites tersimpan di localStorage
- [ ] Download button simulasi progress
- [ ] Empty states tampil dengan benar
- [ ] Responsive di semua breakpoints

---

## 5. Technical Stack

- Single HTML file dengan embedded CSS & JavaScript
- Vanilla JavaScript (no framework)
- Google Fonts: Plus Jakarta Sans
- Font Awesome untuk icons
- CSS Grid & Flexbox untuk layout
- CSS Custom Properties untuk theming
- LocalStorage API untuk persistence