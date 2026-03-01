# Liora Head Spa — CLAUDE.md

## Project Overview
Single-page marketing website for **Liora Head Spa**, Albuquerque's first luxury head spa. The entire site lives in one file: `index.html`.

## File Structure
```
index.html   — all HTML, CSS, and JS in a single file (~1,260 lines)
```
There is no build step, no framework, no package manager. Edit `index.html` directly.

## Brand & Design System

### Voice & Tone
Warm, elevated, intentional. Words like "ritual," "light," "scalp-to-soul," and "restorative" are on-brand. Avoid clinical or generic spa language.

### Color Tokens (CSS custom properties)
| Token        | Value                    | Usage                        |
|--------------|--------------------------|------------------------------|
| `--cream`    | `#FAF6F0`                | Page background              |
| `--ivory`    | `#F2EBE0`                | Alternate section background |
| `--gold`     | `#C9A96E`                | Primary accent, labels, CTAs |
| `--gold-lt`  | `#E2C99A`                | Subtle gold accents          |
| `--gold-dk`  | `#A07840`                | Hover states on gold         |
| `--brown`    | `#3D2B1F`                | Primary headings, dark text  |
| `--brown-lt` | `#6B4C35`                | Secondary text               |
| `--white`    | `#FFFDF9`                | Card backgrounds             |
| `--text`     | `#2E1F14`                | Body copy                    |
| `--muted`    | `#8C7060`                | Subdued text, descriptions   |
| `--border`   | `rgba(201,169,110,0.25)` | Borders and dividers         |

### Typography
- **Headings** — `Cormorant Garamond` (serif), weight 300–400, often italic for emphasis
- **Body / UI** — `Jost` (sans-serif), weight 300–500
- **Labels** — Jost, `0.72rem`, `font-weight: 500`, `letter-spacing: 0.18em`, uppercase, gold color
- Both fonts loaded from Google Fonts

### Layout
- `.container` — max-width `1100px`, centered, `padding: 0 2rem`
- `.section` — `padding: 7rem 0`
- `.section--sm` — `padding: 4.5rem 0`
- `.gold-line` — decorative gradient divider with a small circle SVG icon

### Buttons
- `.btn-primary` — dark brown background, warm white text
- `.btn-outline` — gold border, gold text; fills gold on hover
- `.nav-cta` — gold background nav button (Book Now)

### Animations
- `.fade-in` elements animate in via IntersectionObserver (add class `animate-ready` + `visible`)
- Fallback fires after 800ms for iframe/preview contexts

## Page Sections (in order)
1. **Nav** — fixed, transparent over hero, becomes frosted-glass on scroll. Desktop + hamburger mobile menu.
2. **Hero** (`#hero`) — full-viewport, centered, gold logo mark SVG
3. **Services** (`#services`) — grid of service cards with pricing
4. **About** (`#about`) — brand story
5. **Membership** (`#membership`) — three membership tiers
6. **Signup** (`#signup`) — MailChimp email list embed
7. **FAQ** (`#faq`) — accordion
8. **Contact** (`#contact`) — contact details (form is commented out, pending re-enable)
9. **Footer** — logo, navigation, hours, Instagram link

## Floating Elements
- **Hiring card** (`#hiringCard`) — fixed bottom-right corner, dismissible. Contains "Now Hiring" call to action directing applicants to `morgann@lioraheadspa.com?subject=Application%20%E2%80%93%20Liora%20Head%20Spa`. Weekend availability note included.
- **Booking modal** (`#bookingModal`) — "Coming Soon" modal triggered by Book Now buttons; links to email list signup

## Third-Party Integrations
- **MailChimp** — email list signup form (`#signup` section)
- **Mangomint** — booking system; triggered via hidden `#mangomint-trigger` anchor. Currently shows a "coming soon" modal instead.
- **Google Fonts** — Cormorant Garamond + Jost

## Key Contacts
- General inquiries: `hello@lioraheadspa.com`
- Job applications: `morgann@lioraheadspa.com`
- Phone: (505) 500-4090
- Address: 8000 Paseo del Norte Blvd NE, Suite C9, Albuquerque, NM 87122
- Instagram: [@lioraheadspa](https://www.instagram.com/lioraheadspa)

## Hours
- Wed – Sat: 10am – 7pm
- Sun: 10am – 5pm
- Mon – Tue: Closed

## Notes
- The contact form HTML exists but is commented out — re-enable when ready
- Email addresses in the contact section are HTML entity-encoded to deter scrapers
- No JavaScript frameworks — vanilla JS only
- `index.html` exceeds 256KB; use `offset` + `limit` when reading with tools
