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
- 💾 Session state saved with browser `localStorage`
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

The website stores only these values in browser `localStorage`:

```text
response
selectedDate
selectedTime
location
```

If saved data is missing or invalid, the website automatically returns the user to the first incomplete step instead of showing a broken confirmation page.

## Technologies

- HTML5
- CSS3
- Vanilla JavaScript
- Browser Local Storage
- No external framework or backend required

## Notes

This is a front-end-only project. No personal information is sent to a server or external API.

Made with ☕❤️
