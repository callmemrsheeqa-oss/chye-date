# Chai Meetup ☕❤️

A cute interactive chai meetup website with a playful **Yes / No** interaction and a complete 5-step planning flow.

## Project Flow

The website guides the user through:

1. **Chai Invitation** — “Would you like to have chai with me?”
2. **Day Selection** — choose today or a future day
3. **Time Selection** — choose a valid time
4. **Location** — choose where to meet
5. **Final Confirmation** — review and confirm the chai meetup

## Features

- ❤️ Interactive **Yes / No** invitation
- 😌 The **No** button moves to a random position when approached or clicked
- ☕ Smooth multi-step navigation without page reloads
- 📅 Day validation with past days rejected
- ⏰ Time validation
- 📍 Location validation and whitespace trimming
- ← Back navigation with previous selections preserved
- 🔄 Always opens on the first page, even after a refresh
- 📧 Email notification to the host when the meetup is confirmed
- 🎉 Dynamic confirmation using the selected day, time, and location
- ❤️☕ Final celebration animation with hearts and chai emojis
- 📱 Responsive design for desktop and mobile screens
- 🛡️ Graceful handling of missing or invalid saved state

## Project Structure

```text
chye-date/
├── index.html
└── README.md
```

The project is intentionally lightweight and currently uses a single HTML file containing the HTML, CSS, and JavaScript.

## How to Run

### Option 1 — Open Directly

Download or clone the repository and open `index.html` in a modern web browser.

### Option 2 — Run with VS Code

1. Clone the repository.
2. Open the project folder in VS Code.
3. Open `index.html` in a browser.
4. For the best development experience, use a local server such as the VS Code Live Server extension.

## Validation & Navigation

### Step 1 — Invitation

- The **Yes ❤️** button records the response as `Yes`.
- The user is immediately taken to day selection.
- The **No 😌** button is not treated as a valid response.
- When the user tries to interact with **No**, it moves to another position inside the visible viewport.

### Step 2 — Day

A day is required before continuing.

- Today and future days are accepted.
- Past days are rejected.
- The Continue button remains disabled until a valid day is selected.

### Step 3 — Time

A valid hour and minute are required.

- The Continue button remains disabled until a valid time is selected.

### Step 4 — Location

The location must contain at least two meaningful characters.

- Leading and trailing spaces are removed before saving.
- Empty or whitespace-only values are rejected.

### Step 5 — Confirmation

The final screen is generated from the actual saved values.

Example:

> Great! 🎉❤️ You have planned a chai meetup for 15 October 2026 at 6:00 PM at ABC Cafe. Shall we meet there at this time? ☕

After confirmation:

> Perfect! ❤️☕ It's officially a chai meetup!

## State Management

Progress is kept in memory only while the page is open. Every time the site is opened or refreshed it starts again from the first page.

## Technologies

- HTML5
- CSS3
- Vanilla JavaScript
- No external framework or backend required

## Notes

This is a front-end-only project with one exception: when the final confirmation button is pressed, the chosen day, time and location are sent once through the FormSubmit.co email service to the host's inbox, so the host knows the chai meetup was confirmed. Nothing else is collected.

### Email notification setup

1. Host the site on GitHub Pages (or any web server) and open it once.
2. Press the final confirmation button yourself. FormSubmit sends an activation email to the address set in `NOTIFY_EMAIL` in `index.html`.
3. Click the activation link in that email. After that, every confirmation arrives in that inbox. Check spam if it doesn't appear.

Made with ☕❤️
