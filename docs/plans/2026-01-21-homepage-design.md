# Homepage Design (Single Card)

## Goal
Create a simple, one-screen academic homepage for a bilingual CN/EN profile.

## Content
- Name: Chinese name line with English name below ("Mingjian Zhang")
- Title/Affiliation: CN line + EN line ("M.S. Student in Artificial Intelligence, BUPT")
- Research keywords (EN): Artificial Intelligence, NLP, LLM
- Contact: email mailto link

## Layout
- Single centered card occupying one screen
- Vertical stack: name -> title/affiliation -> keywords -> contact
- Responsive width with comfortable padding

## Visual Direction
- Warm paper-like background gradient with subtle vignette
- Card with thin border, light shadow, modest radius
- Serif font for the name, clean sans for supporting text
- Minimal motion: gentle page-load fade/slide for the card and text

## Accessibility
- Semantic structure: main, h1, p, address
- Strong contrast and visible focus states
- Base font size >= 16px

## Implementation Notes
- Files: index.html + styles.css
- Define CSS variables for colors, spacing, shadow, and typography
- No JavaScript required
