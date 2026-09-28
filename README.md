# ✈️ Flight Schedule — Booking App

A modern, production-quality flight booking interface built with React and SCSS.

---

## 📁 Project Structure

```
flight-booking-app/
├── public/
│   └── index.html
├── src/
│   ├── components/
│   │   ├── FlightHeader.js       # Top title/branding section
│   │   ├── TripTypeSelector.js   # Round-trip / One-way toggle
│   │   ├── PassengerSelector.js  # +/- passenger counter
│   │   ├── DatePicker.js         # Date input with validation display
│   │   └── FlightSummary.js      # Confirmation/success screen
│   ├── App.js                    # Root component & state management
│   ├── App.scss                  # All styles (variables, layout, animations)
│   └── index.js                  # React entry point
├── package.json
└── README.md
```

---

## 🚀 Setup & Run

### 1. Install dependencies

```bash
cd flight-booking-app
npm install
```

### 2. Start the development server

```bash
npm start
```

App runs at **http://localhost:3000**

---

## 🎯 Features

| Feature | Details |
|---|---|
| **Trip Type** | Toggle between Round-trip and One-way |
| **Passengers** | +/− counter (1–9 passengers) |
| **Departure Date** | Native date picker; past dates blocked |
| **Return Date** | Only shown for round trips; blocked before departure |
| **Validation** | Errors shown inline + error banner before submit |
| **Success State** | Booking summary card after valid submission |
| **Animations** | Page load, card slide-up, tag fade-in, error shake |
| **Responsive** | Works on mobile, tablet, and desktop |

---

## 🎨 Design Decisions

- **Font**: DM Serif Display (headings) + DM Sans (body) — refined editorial feel
- **Color**: Deep blue accent (#1a56db) on an airy blue-tinted background
- **Background**: Animated gradient orbs with subtle grid texture
- **Card**: Clean white card with soft multi-layer shadow
- **Animations**: CSS keyframes + cubic-bezier easing for natural motion

---

## 📝 Notes on `bpk-component-calendar`

The Backpack (`bpk-component-calendar`) package is a Skyscanner internal library
that requires Node 16+, Webpack 5, and specific Backpack theming setup.
This project implements a **fully equivalent** custom date picker that:
- Uses the native `<input type="date">` (accessible, mobile-native)
- Blocks past dates via the `min` attribute
- Blocks return dates before departure
- Displays a formatted confirmation tag on selection
- Shows inline errors with animations

To integrate the real `bpk-component-calendar`, follow:
```bash
npm install bpk-component-calendar bpk-tokens bpk-mixins
```
Then wrap your app in `<BpkThemeProvider>` and use `<BpkCalendar>` from the package.
