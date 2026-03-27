# Xyrr Investments — Design System

## Color Palette

| Token            | Hex       | Usage                              |
|------------------|-----------|------------------------------------|
| bg-primary       | #0B1120   | Page background                    |
| bg-section-alt   | #111827   | Alternating section background     |
| bg-card          | #1A2332   | Deal cards, stat boxes             |
| bg-card-border   | #2A3444   | Card borders                       |
| accent-gold      | #C9A84C   | Buttons, highlights, accent lines  |
| accent-gold-dark | #A6882E   | Button hover state (CSS only)      |
| text-primary     | #FFFFFF   | Headlines, primary text            |
| text-secondary   | #B0BEC5   | Body text, descriptions            |
| text-muted       | #6B7B8D   | Footer text, minor labels          |
| tag-bg           | #1E2D3D   | Strategy tag background            |
| tag-text         | #C9A84C   | Strategy tag text                  |

## Typography

| Element        | Font              | Weight | Size (desktop) | Size (mobile) | Line Height |
|----------------|-------------------|--------|----------------|---------------|-------------|
| h1 (hero)      | Inter, sans-serif | 800    | 56px           | 36px          | 1.1         |
| h2 (section)   | Inter, sans-serif | 700    | 40px           | 28px          | 1.2         |
| h3 (card title)| Inter, sans-serif | 600    | 20px           | 18px          | 1.3         |
| body           | Inter, sans-serif | 400    | 17px           | 16px          | 1.7         |
| small/label    | Inter, sans-serif | 500    | 14px           | 13px          | 1.4         |
| stat number    | Inter, sans-serif | 800    | 32px           | 24px          | 1.1         |
| stat label     | Inter, sans-serif | 400    | 15px           | 14px          | 1.4         |
| button         | Inter, sans-serif | 700    | 15px           | 14px          | 1.0         |

## Spacing Scale

| Token | Value |
|-------|-------|
| xs    | 8px   |
| sm    | 16px  |
| md    | 24px  |
| lg    | 40px  |
| xl    | 64px  |
| xxl   | 96px  |

## Layout

- Max content width: 1200px
- Section vertical padding: 96px (desktop), 64px (mobile)
- Card grid gap: 24px
- Card padding: 28px
- Card border-radius: 10px
- Button padding: 14px 32px
- Button border-radius: 6px
- Stat box padding: 28px
- Stat box border-radius: 10px

## Section Specifications

### 1. Hero
- Full viewport height: 100vh
- Centered vertically and horizontally
- Company name: h1, uppercase, letter-spacing 6px
- Tagline: body size, text-secondary color, max-width 600px
- Sub-tagline: small size, text-muted color
- Two buttons side-by-side, 12px gap
- Primary button: gold bg, dark text (#0B1120)
- Secondary button: transparent bg, gold border, gold text
- Thin gold horizontal rule (2px, 60px wide) between name and tagline

### 2. About
- bg-section-alt background
- Headline centered, gold underline accent (3px, 50px wide, centered)
- Body text centered, max-width 720px
- Three stat boxes in a row (grid, 3 cols desktop, 1 col mobile)
- Stat boxes: bg-card background, border 1px bg-card-border
- Number in accent-gold, label in text-secondary

### 3. Active Deals
- bg-primary background
- Headline centered with gold underline accent
- 3-column grid (desktop), 1-column (mobile)
- Cards: bg-card, 1px border bg-card-border, border-radius 10px
- Card layout top-to-bottom: address (h3), city (small, text-muted), specs line, price line (accent-gold, large), ARV line, note line (if present), strategy tags row, [GET DETAILS] button
- Strategy tags: pill-shaped, tag-bg background, tag-text color, 6px 14px padding, border-radius 20px
- Price displayed at stat-number size
- GET DETAILS button: full-width, gold bg, dark text

### 4. Contact
- bg-section-alt background
- Headline centered with gold underline accent
- Body text centered, max-width 600px
- Three info blocks in a row: icon + label, text-secondary
- SEND MESSAGE button: gold bg, dark text, centered

### 5. Footer
- bg-primary background, top border 1px bg-card-border
- Padding: 40px vertical
- Two lines of text, centered, text-muted color
- Font size: small

## General Rules
- No animations, transitions, or hover effects
- No JavaScript
- No external dependencies (fonts loaded via Google Fonts link only)
- Fully responsive via CSS Grid and Flexbox
- Semantic HTML5 structure
