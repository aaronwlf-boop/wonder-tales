# WonderTales: Read & Count Safari 🦁📚🔢

**WonderTales: Read & Count Safari** is an interactive, ad-free educational web application created for 6-year-olds (Kindergarten & Grade 1). It blends early childhood literacy (tap-to-read stories and phonics spelling) with foundational early math skills (visual counting, addition, and subtraction within 10), powered by natural audio narration and rewarding gamification.

---

## 🌟 Features

### 📖 1. Interactive Story Time (Early Literacy)
- **Word-by-Word Reading:** Children can tap on any individual word in a sentence to highlight it and hear its pronunciation.
- **Cheery Bedtime-Style Narration:** Plays full stories with warm, natural voices and real-time karaoke-style word highlighting.
- **Comprehension Micro-Challenges:** Quick interactive questions after each page to check understanding without causing frustration.

### 🔤 2. Phonics & Sight Words Lab
- **Touch-Friendly Letter Blocks:** Large, colorful letter tiles designed for small fingers and developing fine motor skills.
- **Phonics Reinforcement:** Tap letters to hear phonics sounds while building common 3-letter CVC (Consonant-Vowel-Consonant) sight words.
- **Immediate Affirmation:** Encouraging auditory and visual prompts when a word is completed correctly.

### 🔢 3. Math Quest (Concrete Visuals & Manipulatives)
- **123 Count Mode:** Tap-to-count animated animals (frogs, monkeys, ducks, apples) with numbered markers that appear as the child counts.
- **➕ Addition Safari:** Visual groups with concrete representations reinforcing sums up to 10 ($a + b \le 10$).
- **➖ Takeaway Subtraction:** Visually crosses out items to clearly show subtraction concepts ($a - b$).
- **Four Big Multi-Choice Answers:** Styled with high contrast and friendly spacing.

### 🏆 4. Safari Badge Collection & Gamification
- Collect shiny golden stars for completing story pages, spelling words, and solving math problems.
- Unlock badges:
  - 🦁 **Lion Cub Reader**
  - 🔤 **Spelling Champ**
  - 🐒 **Monkey Counter**
  - 👑 **Safari Grand Explorer**
- Persistent progress saved automatically to browser `localStorage` with a kid-safe parental reset button.
- Colorful confetti celebrations powered by Canvas Confetti.

---

## 🔊 Audio Pipeline & iOS / Safari Compatibility

Audio playback on mobile devices—specifically **iOS Safari and WebKit**—enforces strict autoplay and gesture-activation policies. WonderTales implements an audio engine that handles these restrictions:

1. **Pre-Warmed Audio Context:** A unified `AudioContext` is unlocked on the user's first touch event (`touchstart`/`click`) via a silent 1-sample buffer.
2. **Pre-Authorized HTML5 Media Element:** A reusable `<audio>` element with `playsinline` and `webkit-playsinline` attributes is pre-primed with silent data to preserve iOS media playback privileges across asynchronous TTS fetches.
3. **Dual-Engine Speech Architecture:**
   - **Gemini TTS (`gemini-2.5-flash-preview-tts`):** High-fidelity AI speech synthesis with expressive tone prompts and 16-bit PCM $\rightarrow$ WAV binary conversion.
   - **Native Web Speech Fallback:** Automatically switches to device-native voices (such as Apple's "Samantha", "Daniel", or Google's English voice packs) if offline, unauthenticated, or rate-limited.
4. **Synthesized Web Audio Chimes:** Sound effects (success fanfare, gentle pops, and encouraging boops) are generated in real-time via oscillator synthesis, requiring no external sound assets.

---

## 🚀 Getting Started

### Local Setup (No Build Tools Required)
1. Clone or download this repository:
   ```bash
   git clone https://github.com/your-username/wondertales-safari.git
   cd wondertales-safari
   ```
2. Open `index.html` directly in any modern web browser:
   - Double-click `index.html`, or
   - Use a local server (optional):
     ```bash
     # Python 3
     python -m http.server 8000
     ```
   - Open your browser to `http://localhost:8000`.

---

## 🌐 Deployment Options

Because the entire app is self-contained in a single file (`index.html`), deployment takes under two minutes:

### 1. GitHub Pages (Free)
1. Push `index.html` to a GitHub repository.
2. Go to **Settings** $\rightarrow$ **Pages**.
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`.
4. Select the `main` or `master` branch and folder `/ (root)`, then click **Save**.
5. Your live app will be published at `https://<your-username>.github.io/<repo-name>/`.

### 2. Netlify Drop (Instant Drag & Drop)
1. Go to [Netlify Drop](https://app.netlify.com/drop).
2. Place `index.html` in a folder named `wondertales`.
3. Drag and drop the folder into the upload box on Netlify.
4. Your site will be deployed instantly with a public HTTPS URL.

### 3. Vercel
1. Install the Vercel CLI:
   ```bash
   npm i -g vercel
   ```
2. Run `vercel` in your project folder and follow the prompts.

---

## 🛠️ Technology Stack

| Layer | Technology |
|---|---|
| **Structure & Logic** | Single-file HTML5 + Vanilla ES6 JavaScript |
| **Styling & Design** | [Tailwind CSS CDN](https://tailwindcss.com/) with playful custom typography (`Fredoka` & `Quicksand` via Google Fonts) |
| **Icons & Visuals** | [Font Awesome 6](https://fontawesome.com/) + Vibrant Unicode Emojis |
| **Celebrations** | [Canvas Confetti](https://www.npmjs.com/package/canvas-confetti) |
| **Primary TTS Voice** | Google Gemini TTS (`gemini-2.5-flash-preview-tts` / voice: `Puck`) |
| **Fallback Speech** | Web Speech API (`SpeechSynthesisUtterance`) |
| **SFX** | Web Audio API Oscillator Nodes (`triangle`, `sine`) |
| **Storage** | Browser `localStorage` |

---

## 🔒 Safety & Privacy

- **100% Ad-Free:** No tracking scripts, analytics beacons, or third-party advertisements.
- **Child-Safe:** No external chat interfaces, open links, or in-app purchases.
- **Privacy-First:** User progress (stars, completed words, badges) is stored entirely in the user's browser local storage.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and distribute it for educational and non-commercial purposes.