# Mirror v1.0.0 — Be Yourself. Look Fucking Cool.

A confidence-first AI-powered wardrobe app. Upload your entire closet, generate outfits for any occasion, get honest AI critiques, and build confidence in every look.

## Features

### Core
- **Wardrobe Upload** — photo capture/upload for clothing, shoes, accessories, bags, jewelry, hats
- **AI Outfit Generation** — GPT-4o Vision generates 3 outfit options based on occasion, mood, dress code
- **Outfit Builder + AI Critique** — build your own look, get positive/negative feedback and swap suggestions
- **Style-Adaptive Theming** — app visuals match your style (minimal, bold, comfy, dark)
- **Weather Awareness** — auto-pulls current weather, factors into outfit suggestions

### Wardrobe Management
- **Availability Tracking** — toggle items available/unavailable
- **Laundry Tracker** — mark items clean/dirty, low-wardrobe warnings
- **Brand/Price Tracking** — tag items with brand, price, purchase date
- **Cost-Per-Wear Analytics** — price ÷ times worn, color-coded
- **Batch Scan Import** — photograph your closet, AI detects and categorizes all items
- **Seasonal Rotation** — seasonal essentials guide, capsule wardrobe recommendations

### Outfits & Styling
- **Saved Outfits** — save generated or custom-built outfits
- **Outfit Calendar** — plan outfits for upcoming days/events
- **Outfit of the Day** — daily AI suggestion based on weather + calendar + style history
- **Outfit Remix** — "5 ways to wear this jacket" mode
- **Outfit Voting** — A vs B matchup, vote on which to wear
- **Virtual Try-On** — slot-based outfit builder, export as PNG
- **Share as Image** — canvas-rendered branded PNG cards

### Intelligence
- **Style Learning** — AI adapts based on saved/liked outfits over time
- **Color Palette Intelligence** — color theory rules in AI prompts
- **Dress Code Logic** — 7 dress codes with specific AI rules
- **AI Style Report** — monthly recap: style score, personality, color story, suggestions
- **Smart Packing** — AI builds capsule travel wardrobe from your closet

### Social & Gamification
- **Community Feed** — share outfit codes, import friends' looks
- **Style Challenges** — daily rotating challenges with streak tracking
- **Wishlist & Shopping Gaps** — auto-detects weak wardrobe categories

### Onboarding
- **Image-Based Style Quiz** — visual cards for vibe, expression, adventure level
- **Name Personalization** — greeting throughout the app

## Tech Stack
- **Frontend**: Vanilla JS, CSS custom properties, PWA (Service Worker + IndexedDB)
- **Backend**: Cloudflare Pages Functions (serverless)
- **AI**: OpenAI GPT-4o Vision API
- **Mobile**: Capacitor for Android + iOS native packaging
- **Storage**: IndexedDB (client-side), localStorage for preferences

## Quick Start

```bash
npm install
npm run dev
```

Visit `http://localhost:8788`

## Environment Variables

Set `OPENAI_API_KEY` in your Cloudflare Pages environment or `.dev.vars` file.

## Mobile Packaging

```bash
npm install
npx cap sync
npx cap open android   # Opens Android Studio
npx cap open ios       # Opens Xcode
```

### Generating Native Icons
```bash
# Place icon files in public/icons/ first, then:
npx @capacitor/assets generate
```

## API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/generate-outfit` | POST | Generate outfit suggestions (1/3/5 depending on mode) |
| `/api/critique-outfit` | POST | AI critique of user-built outfits |
| `/api/detect-items` | POST | Batch wardrobe scanning via photo |
| `/api/style-report` | POST | AI-generated monthly style report |
| `/api/smart-pack` | POST | AI travel packing list builder |

## Project Structure

```
Mirror/
├── public/
│   ├── index.html          # Splash page
│   ├── onboarding.html     # Style quiz
│   ├── wardrobe.html       # Wardrobe management
│   ├── generate.html       # AI outfit generation
│   ├── builder.html        # Manual outfit builder
│   ├── saved.html          # Saved outfits
│   ├── calendar.html       # Outfit calendar
│   ├── board.html          # Profile & analytics
│   ├── ootd.html           # Outfit of the Day
│   ├── community.html      # Social feed
│   ├── challenges.html     # Style challenges
│   ├── packing.html        # Smart packing
│   ├── tryon.html          # Virtual try-on
│   ├── css/mirror.css      # All styles (theme-aware)
│   ├── js/app.js           # All application logic
│   ├── sw.js               # Service worker
│   ├── manifest.json       # PWA manifest
│   └── icons/              # App icons (192, 512, maskable, favicon)
├── functions/
│   └── api/                # Cloudflare Pages Functions
│       ├── generate-outfit.js
│       ├── critique-outfit.js
│       ├── detect-items.js
│       ├── style-report.js
│       └── smart-pack.js
├── capacitor.config.ts     # Capacitor native config
└── package.json
```

## License

Built with chaos, honesty, and zero body-shaming.
