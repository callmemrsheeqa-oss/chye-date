# Chai Invitation ☕❤️

A cute interactive chai invitation website with a playful **YES / NO** question and a 5-step planning flow. When the invitation is confirmed, the host receives an email with the chosen day, time and location.

## Project Flow

1. **Invitation** — "Will you have chai with me?"
2. **Day** — choose today or a later day
3. **Time** — choose hour, minute and AM/PM
4. **Location** — type where to meet
5. **Confirmation** — review the plan and confirm it

Steps change with a smooth slide and fade, without reloading the page.

## Features

- ❤️ **YES ❤️** moves straight on to the next step
- 😌 The **NO** button runs away to a random spot on screen and can never be selected
- ✅ Validation on every step, with friendly messages
- ← **Back** button on steps 2–4 that keeps earlier choices
- 🔄 Always opens on the first page, even after a refresh
- 📧 **Confirmation email** to the host when the invitation is confirmed
- 🎉 Confirmation message built from the real day, time and location
- ❤️☕ Falling hearts and chai emojis after confirming
- 🌗 Dark and light colour schemes that follow the device setting
- 📱 Responsive layout for phones and desktops
- 🧘 Animations are skipped for people who prefer reduced motion

## Validation

| Step | Rule | Message |
| --- | --- | --- |
| 2 — Day | A day is required. Past days are rejected. Continue stays disabled until a valid day is chosen. | `Please choose a day for our chai ☕❤️` |
| 3 — Time | Hour, minute and AM/PM are all required. | `Ab time bhi select karo ☕⏰` |
| 4 — Location | At least 3 characters. Extra spaces are trimmed and whitespace-only input is rejected. | `Chai kahan peeni hai? Location batao 📍☕` |
| 5 — Confirmation | Only opens when all values are valid. Otherwise the visitor is sent back to the first incomplete step. | — |

## Confirmation Email

When the visitor presses **Yes, let's have chai! ❤️☕**:

- One email with the subject **Submitted invitation** is sent to the address set in `NOTIFY_EMAIL` in `index.html`.
- It contains the response, day, time, location and the time of confirmation.
- It is sent only once per confirmation. If sending fails, the visitor sees the reason and a **Try sending again** button.
- The button is disabled briefly after clicking to prevent duplicate submissions.

The email is sent through [FormSubmit](https://formsubmit.co), so no backend is needed.

### One-time setup

1. Host the site on GitHub Pages (or any web server) and open it from its web address.
2. Go through the steps and press the final button once yourself. FormSubmit sends an activation email to the address in `NOTIFY_EMAIL`.
3. Click the activation link in that email. After that, every confirmation arrives in that inbox. Check the spam folder if nothing shows up.

### Optional: custom sender name

FormSubmit always shows its own name as the sender. To show **Submitted Invitation** instead, get a free access key from [Web3Forms](https://web3forms.com) and paste it into `index.html`:

```js
var WEB3FORMS_KEY = "your-access-key";
```

While this value is empty, FormSubmit is used.

## Project Structure

```text
chye-date/
├── index.html      # HTML, CSS and JavaScript in one file
├── package.json
└── README.md
```

## How to Run

The page works when opened in a browser, but the confirmation email only works when the site is opened from a web address.

- **GitHub Pages:** in the repository go to **Settings → Pages**, choose the `main` branch and the `/ (root)` folder, then open the published address.
- **Locally:** use a small local server such as the VS Code **Live Server** extension. Opening `index.html` directly as a file will show the page, but sending the email will fail.

## Technologies

- HTML5, CSS3 and vanilla JavaScript, with no framework
- Google Fonts (Fraunces and Nunito)
- FormSubmit (or optionally Web3Forms) for the confirmation email

## Privacy

Nothing is stored in the browser between visits. The only data that leaves the page is the chosen day, time and location, sent once to the host's inbox when the invitation is confirmed.

Made with ☕❤️
