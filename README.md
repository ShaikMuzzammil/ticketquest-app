# 🎟️ Ticket Quest — All-in-One Booking Platform

**Movies · Events · Sports · Theaters**

A modern, responsive web application for booking tickets to movies, live events, sports matches, and exploring premium theaters. Features an interactive booking wizard, 3D‑like flip cards, animated backgrounds, and a seamless multi‑step checkout.

---

## 📌 Project Overview

Ticket Quest is a front‑end ticketing solution that simulates a complete booking experience. Users can browse upcoming movies, events, and sports, select seats (for movies), choose ticket types, add snacks, and complete a payment flow – all with beautiful animations and a fully responsive design.

---

## ✨ Key Features

| Category | Features |
|----------|----------|
| **Movies** | – Browse recommended movies with ratings and genres<br>– Book tickets: select city → theater → time → seats → snacks → payment<br>– Seat grid with occupied/available toggling<br>– Real‑time price calculation |
| **Events** | – Filter events by category (concerts, festivals, sports, comedy, etc.)<br>– Choose ticket type (VIP/Standard/Economy) and quantity<br>– Secure payment simulation with card details<br>– Print ticket after booking |
| **Sports** | – Dedicated page for elite sports events<br>– Same booking flow as events (ticket type, quantity, payment)<br>– Event‑specific pricing |
| **Theaters** | – 10 premium theaters with automatic flip‑cards on hover<br>– Front: image, name, location, features, description<br>– Back: interesting "Did You Know?" facts |
| **General** | – Animated gradient backgrounds with floating particles<br>– Persistent login simulation (localStorage)<br>– Fully responsive (mobile/tablet/desktop)<br>– Print ticket functionality<br>– Back button on every page |

---

## 🧭 Pages & Navigation

| Page | File | Description |
|------|------|-------------|
| **Home** | `body.html` | Hero banner + movie/event/sport cards + main booking modal (shared logic) |
| **Movies** | `movie.html` | Dedicated movie listing + complete movie booking flow |
| **Events** | `events.html` | Filterable events grid + event booking flow |
| **Sports** | `sports.html` | Sports events listing + event booking flow (same as events) |
| **Theaters** | `theaters.html` | Flip‑card gallery of 10 premium theaters with fun facts |
| **About Us** | `aboutus.html` | Vision, mission, feature highlights |

All pages share a consistent dark theme, gradient animations, and a fixed **back button** for easy navigation.

---

## 🎬 Detailed Booking Flows

### Movie Booking (5 steps)

1. **Select City** – Chennai, AP, Bangalore, Hyderabad, Delhi (with city images)
2. **Select Theater & Time** – PVR, INOX, Cinepolis + 4 time slots
3. **Select Seats** – 5×10 grid; occupied seats disabled; click to select/unselect
4. **Add Snacks** – Popcorn, Nachos, Cola, Hot Dog, Chocolate, Ice Cream (with prices)
5. **Payment & Ticket** – Review total, proceed to pay → get transaction ID + printable ticket

> **Price:** $12 per seat + snacks cost. Validation at each step.

### Events & Sports Booking (4 steps)

1. **Select Ticket Type** – VIP / Standard / Economy (prices vary per event)
2. **Select Quantity** – 1–10 tickets (increment/decrement buttons)
3. **Select Payment Method** – Credit Card, Debit Card, PayPal, UPI
4. **Enter Card Details** – Cardholder name, number, expiry, CVV (basic validation)
5. **Confirmation** – Transaction ID + reference code + printable ticket

> **All prices are pre‑defined per event** (e.g., Champions League Final: VIP $150, Standard $80, Economy $50).

---

## 🎭 Theaters Flip Cards

The `theaters.html` page displays 10 famous theaters. Each card:

- **Front** – Image, name, location, feature tags (e.g., Dolby Atmos, IMAX, Historic), description.
- **Back** – An interesting fact (e.g., “The original Globe Theatre burned down in 1613…”).
- **Interaction** – Hover to flip (CSS 3D transform); click the **X** button to flip back.

**Theaters included:**  
Royal Opera House (Mumbai), The Globe Theater (London), Majestic Broadway (NYC), Sydney Opera House, Teatro alla Scala (Milan), Bolshoi Theater (Moscow), Palais Garnier (Paris), Metropolitan Opera (NYC), Elgin Theatre (Toronto), National Theatre (London).

---

## 🛠️ Technology Stack

| Layer | Technology |
|-------|------------|
| Markup | HTML5 |
| Styling | CSS3 (custom properties, grid/flexbox, keyframe animations, 3D transforms) |
| Interactivity | JavaScript (ES6) – DOM manipulation, event handling, localStorage |
| Icons | Font Awesome 6 |
| Fonts | Google Fonts – Poppins |
| Images | Unsplash (external) + local PNG assets |

> **No backend / database** – perfect for static hosting (GitHub Pages, Netlify, Vercel).

---

## 📁 Asset Requirements

Place the following images in the **same folder** as the HTML files (or adjust paths):

- `chennai.png`, `ap.png`, `bng.png`, `hyd.png`, `taj.png`
- `popcorn.png`, `cheese.png`, `cola.png`
- `rrr.png`, `saaho.png`, `narnia.png`, `mazerunner.png`, `jack.png`, `avengers.png`, `radheshyam.png`
- `salaar.png`, `devara.png`, `kalki.png`
- `sunberg.png`, `technosummit.png`, `coldplay.png`, `techno.png`
- `las.png`, `football.png`, `tennis.png`, `baseball.png`
- `theater2.png`, `theater5.png`, `theater7.png`, `theater8.png`, `majestic.png`
- `art.png`, `marathon.png`

External images (Unsplash) will load automatically.

---

## 🚀 How to Run Locally

1. **Download** or clone the repository.
2. Place all HTML files and images in a single folder.
3. Open `body.html` (or any page) directly in your browser – no server required.
4. For the best experience, start with `body.html` as the main entry point.

> 💡 **Tip:** To test login simulation, open browser console and run:  
> `localStorage.setItem('username', 'YourName');` then refresh the page.

---

## 📱 Responsive Design

| Device | Layout |
|--------|--------|
| **Desktop (>1200px)** | 3–4 card grid, full layout |
| **Tablet (768px–1200px)** | 2–3 card grid, reduced font sizes |
| **Mobile (<768px)** | 1 card per row, simplified seat grid (4 columns), modal padding reduced |
| **Small mobile (<480px)** | Further font and spacing adjustments |

All pages are tested to work on screens from 320px to 1920px.

---

## 🖨️ Printing Tickets

After a successful booking, a **Print Ticket** button appears. Clicking it opens a new window with a styled ticket containing:

- Event/movie name
- Selected options (city, theater, time, seats, snacks, ticket type, quantity)
- Total paid amount
- Transaction ID and reference code
- Simulated barcode

The browser’s print dialog then allows physical printing or saving as PDF.

---

## 🔧 Customization Guide

| What to change | Where to edit |
|----------------|---------------|
| Add a new movie | `.movies-grid` in `body.html` or `movie.html` – duplicate a `.movie-card` block |
| Change seat price | `const ticketPricePerSeat = 12;` in `movie.html` |
| Modify event ticket prices | `eventTicketTypes` object in `events.html` or `sports.html` |
| Add a theater card | `.theater-card` block in `theaters.html` – update front/back content |
| Adjust animation speeds | Look for `@keyframes` rules in the `<style>` section |

---

## 🌐 Live Demo

You can host the project on any static web server:

- **GitHub Pages** – Push the folder to a repository and enable Pages.
- **Netlify** – Drag & drop the folder.
- **Vercel** – Same process.

Set the entry point to `index.html`.

---

## 📄 License

This project is for **educational and demonstration purposes only**.  
All images, trademarks, and event names are the property of their respective owners.  
No commercial use is implied.

---

<div align="center">

Made with ❤️ for entertainment lovers  
**Ticket Quest – Your Gateway to Unforgettable Experiences**

</div>
