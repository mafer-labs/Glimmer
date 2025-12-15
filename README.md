# Glimmer 

A minimalist Progressive Web App (PWA) designed to help users capture "glimmers"—micro-moments of safety, joy, and calm—to combat stress and negative bias.

**[✨ View Live App](https://mafer-labs.github.io/Glimmer/)**

![Version](https://img.shields.io/badge/version-8.0-teal)
![Status](https://img.shields.io/badge/status-live-success)
![License](https://img.shields.io/badge/license-MIT-blue)

## 📖 About The Project

Glimmer is built on the principle of neuroplasticity: by actively looking for small positive moments, we can retrain the brain to scan for safety rather than danger.

It operates entirely client-side, meaning no user data is ever sent to a server. Everything is stored locally on the user's device.

## ✨ Key Features

* **Zero-Friction Logging:** One-tap capture mechanism.
* **Gamification (Dopamine):** * **Confetti Celebration:** Visual reward on every capture (using `canvas-confetti`).
    * **Streak Logic:** Tracks consecutive days of activity.
* **Inspiration Engine:** Random "Spark" prompts (💡) to help users with writer's block.
* **Bilingual Support:** Full toggle between English (EN) and Spanish (ES).
* **Data Sovereignty:** * **Local Storage:** 100% private.
    * **Export:** Users can download their full history as a `.txt` file.
* **Sanctuary UI:** Glassmorphism design system using calming aqua/teal gradients.
* **Safety Controls:** Confirmation modals prevent accidental data loss.

## 🛠 Technical Overview

To maintain simplicity and zero hosting costs, the project is architected as a **Single File Component**.

* **Stack:** HTML5, CSS3, Vanilla JavaScript (ES6+).
* **External Libs:** `canvas-confetti` (via CDN).
* **Hosting:** GitHub Pages.

### Data Structure & Persistence
State is managed via `window.localStorage`. 

| Key | Type | Description |
| :--- | :--- | :--- |
| `glimmerCount` | `Integer` | Total items logged. |
| `glimmerStreak` | `Integer` | Current consecutive days. |
| `lastGlimmerDate` | `String` | ISO Date (`YYYY-MM-DD`) of last log. |
| `glimmerLang` | `String` | User preference: `'en'` or `'es'`. |
| `glimmerHistory` | `JSON` | Array of objects `{text, time}`. |

### Logic: Bilingual Dictionary
Text is managed via a `translations` constant containing nested objects for `en` and `es`. Functions `toggleLanguage()` and `updateLanguage()` handle the DOM updates dynamically.

### Logic: Confetti & Prompts
* **Confetti:** Triggered via `fireConfetti()` function on successful capture.
* **Prompts:** A randomized array of strings in the `translations` object is accessed via `inspireMe()`, injecting text into the input placeholder.

## 🚀 How to Run Locally

1.  Clone the repo:
    ```bash
    git clone [https://github.com/mafer-cordovas/Glimmer.git](https://github.com/mafer-cordovas/Glimmer.git)
    ```
2.  Open `index.html` in any web browser.

## 🗺 Roadmap

Future features planned:
- [ ] **Manifest.json:** Full installability with custom splash screen and hidden browser bars.
- [ ] **Visual Analytics:** Bar chart showing glimmers per week.
- [ ] **Social Share:** Generate an image card to share on Instagram Stories.

## 🤝 Contributing

This project is open for personal use and modification.
